# PlaceResTokenInQueue

- ea: `0x18000dd00`
- end: `0x18000dde3`
- name: `PlaceResTokenInQueue`
- size: `227`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000d588`

## callees

- `0x180002594`
- `0x180009c04`
- `0x18000d3ac`
- `0x18000dd00`

## pseudocode

```c
void __fastcall PlaceResTokenInQueue(_QWORD *a1, __int64 a2)
{
  _QWORD *v4; // rdx
  _QWORD *v5; // rcx
  _QWORD *v6; // rsi
  __int64 v7; // r8
  _QWORD *v8; // rdx

  if ( !*(_DWORD *)(a2 + 16) )
    goto LABEL_17;
  v4 = *(_QWORD **)a2;
  if ( v4 )
  {
    do
    {
      v5 = (_QWORD *)v4[2];
      v6 = (_QWORD *)*v4;
      if ( a1[1] == v5[1] && *a1 == *v5 )
      {
        if ( *((_DWORD *)a1 + 4) >= *((_DWORD *)v5 + 4) )
        {
          operator delete(a1);
          return;
        }
        if ( v4 == *(_QWORD **)a2 )
          *(_QWORD *)a2 = v6;
        else
          *(_QWORD *)v4[1] = v6;
        v7 = v4[1];
        if ( v4 == *(_QWORD **)(a2 + 8) )
          *(_QWORD *)(a2 + 8) = v7;
        else
          *(_QWORD *)(*v4 + 8LL) = v7;
        *v4 = *(_QWORD *)(a2 + 24);
        --*(_DWORD *)(a2 + 16);
        *(_QWORD *)(a2 + 24) = v4;
        operator delete(v5);
      }
      v4 = v6;
    }
    while ( v6 );
  }
  v8 = *(_QWORD **)a2;
  if ( !*(_QWORD *)a2 )
  {
LABEL_17:
    CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::AddTail(a2, a1);
    return;
  }
  while ( *((_DWORD *)a1 + 4) > *(_DWORD *)(v8[2] + 16LL) )
  {
    v8 = (_QWORD *)*v8;
    if ( !v8 )
      goto LABEL_17;
  }
  CSPList<CResToken *,CResToken *>::InsertBefore(a2, v8, a1);
}

```

## disassembly

```asm
0x18000dd00  mov     [rsp+arg_0], rbx
0x18000dd05  mov     [rsp+arg_8], rsi
0x18000dd0a  push    rdi
0x18000dd0b  sub     rsp, 20h
0x18000dd0f  cmp     dword ptr [rdx+10h], 0
0x18000dd13  mov     rbx, rdx
0x18000dd16  mov     rdi, rcx
0x18000dd19  jz      loc_18000DDAC
0x18000dd1f  mov     rdx, [rdx]
0x18000dd22  test    rdx, rdx
0x18000dd25  jz      short loc_18000DD90
0x18000dd27  mov     rcx, [rdx+10h]; void *
0x18000dd2b  mov     rsi, [rdx]
0x18000dd2e  mov     rax, [rcx+8]
0x18000dd32  cmp     [rdi+8], rax
0x18000dd36  jnz     short loc_18000DD88
0x18000dd38  mov     rax, [rcx]
0x18000dd3b  cmp     [rdi], rax
0x18000dd3e  jnz     short loc_18000DD88
0x18000dd40  mov     eax, [rcx+10h]
0x18000dd43  cmp     [rdi+10h], eax
0x18000dd46  jnb     short loc_18000DDC7
0x18000dd48  cmp     rdx, [rbx]
0x18000dd4b  jnz     short loc_18000DD52
0x18000dd4d  mov     [rbx], rsi
0x18000dd50  jmp     short loc_18000DD59
0x18000dd52  mov     rax, [rdx+8]
0x18000dd56  mov     [rax], rsi
0x18000dd59  mov     r8, [rdx+8]
0x18000dd5d  cmp     rdx, [rbx+8]
0x18000dd61  jnz     short loc_18000DD69
0x18000dd63  mov     [rbx+8], r8
0x18000dd67  jmp     short loc_18000DD70
0x18000dd69  mov     rax, [rdx]
0x18000dd6c  mov     [rax+8], r8
0x18000dd70  mov     rax, [rbx+18h]
0x18000dd74  mov     [rdx], rax
0x18000dd77  dec     dword ptr [rbx+10h]
0x18000dd7a  mov     [rbx+18h], rdx
0x18000dd7e  mov     edx, 18h; unsigned __int64
0x18000dd83  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000dd88  mov     rdx, rsi
0x18000dd8b  test    rsi, rsi
0x18000dd8e  jnz     short loc_18000DD27
0x18000dd90  mov     rdx, [rbx]
0x18000dd93  test    rdx, rdx
0x18000dd96  jz      short loc_18000DDAC
0x18000dd98  mov     ecx, [rdi+10h]
0x18000dd9b  mov     rax, [rdx+10h]
0x18000dd9f  cmp     ecx, [rax+10h]
0x18000dda2  jbe     short loc_18000DDD6
0x18000dda4  mov     rdx, [rdx]
0x18000dda7  test    rdx, rdx
0x18000ddaa  jnz     short loc_18000DD9B
0x18000ddac  mov     rdx, rdi
0x18000ddaf  mov     rcx, rbx
0x18000ddb2  call    ?AddTail@?$CSPList@PEAUSStrCost@CTnMultiResStringPackage@@PEAU12@@@QEAAPEAXPEAUSStrCost@CTnMultiResStringPackage@@@Z; CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::AddTail(CTnMultiResStringPackage::SStrCost *)
0x18000ddb7  mov     rbx, [rsp+28h+arg_0]
0x18000ddbc  mov     rsi, [rsp+28h+arg_8]
0x18000ddc1  add     rsp, 20h
0x18000ddc5  pop     rdi
0x18000ddc6  retn
0x18000ddc7  mov     edx, 18h; unsigned __int64
0x18000ddcc  mov     rcx, rdi; void *
0x18000ddcf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ddd4  jmp     short loc_18000DDB7
0x18000ddd6  mov     r8, rdi
0x18000ddd9  mov     rcx, rbx
0x18000dddc  call    ?InsertBefore@?$CSPList@PEAUCResToken@@PEAU1@@@QEAAPEAXPEAXPEAUCResToken@@@Z; CSPList<CResToken *,CResToken *>::InsertBefore(void *,CResToken *)
0x18000dde1  jmp     short loc_18000DDB7
```
