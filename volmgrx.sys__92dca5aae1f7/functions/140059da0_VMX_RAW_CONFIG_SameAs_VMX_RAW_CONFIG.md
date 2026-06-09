# VMX_RAW_CONFIG::SameAs(VMX_RAW_CONFIG *)

- ea: `0x140059da0`
- end: `0x140059edb`
- name: `?SameAs@VMX_RAW_CONFIG@@QEAAEPEAV1@@Z`
- size: `315`
- prototype: `unsigned __int8 __fastcall(VMX_RAW_CONFIG *__hidden this, struct VMX_RAW_CONFIG *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140040880`

## callees

- `0x140059da0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140059de8`
- `ntoskrnl!RtlCompareMemory` at `0x140059e0f`
- `ntoskrnl!RtlCompareMemory` at `0x140059de8`
- `ntoskrnl!RtlCompareMemory` at `0x140059e0f`

## pseudocode

```c
unsigned __int8 __fastcall VMX_RAW_CONFIG::SameAs(VMX_RAW_CONFIG *this, struct VMX_RAW_CONFIG *a2)
{
  int v4; // eax
  __int64 v5; // r8
  unsigned __int64 v6; // r10
  __int64 *v7; // r9
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  bool v11; // zf

  if ( *((_DWORD *)this + 19) != *((_DWORD *)a2 + 19) )
    return 0;
  if ( *((_DWORD *)this + 20) != *((_DWORD *)a2 + 20) )
    return 0;
  if ( *((_DWORD *)this + 21) != *((_DWORD *)a2 + 21) )
    return 0;
  if ( RtlCompareMemory((char *)this + 144, (char *)a2 + 144, 0x1Cu) != 28 )
    return 0;
  if ( RtlCompareMemory((char *)this + 172, (char *)a2 + 172, 0x1Cu) != 28 )
    return 0;
  v4 = *((_DWORD *)this + 32);
  if ( v4 != *((_DWORD *)a2 + 32) )
    return 0;
  v5 = *((_QWORD *)this + 17);
  v6 = v5 + 24LL * (unsigned int)(*((_DWORD *)this + 22) * v4);
  v7 = (__int64 *)(v5 + 24LL * (unsigned int)(*((_DWORD *)this + 21) / *((_DWORD *)this + 20)));
  v8 = *((_QWORD *)a2 + 17) + 24LL * (unsigned int)(*((_DWORD *)this + 21) / *((_DWORD *)this + 20));
  while ( (unsigned __int64)v7 < v6 )
  {
    if ( *((_DWORD *)v7 + 3) != *(_DWORD *)(v8 + 12) || *((_DWORD *)v7 + 4) != *(_DWORD *)(v8 + 16) )
      return 0;
    v9 = *v7;
    v10 = *(_QWORD *)v8;
    if ( *v7 )
    {
      if ( !v10
        || *(_DWORD *)(v9 + 16) != *(_DWORD *)(v10 + 16)
        || *(_WORD *)(v9 + 20) != *(_WORD *)(v10 + 20)
        || *(_DWORD *)(v9 + 28) != *(_DWORD *)(v10 + 28) )
      {
        return 0;
      }
      v11 = *(_QWORD *)(*(_QWORD *)(v9 + 40) + 24LL) == *(_QWORD *)(*(_QWORD *)(v10 + 40) + 24LL);
    }
    else
    {
      v11 = v10 == 0;
    }
    if ( !v11 )
      return 0;
    v7 += 3;
    v8 += 24;
  }
  return 1;
}

```

## disassembly

```asm
0x140059da0  mov     [rsp+arg_0], rbx
0x140059da5  push    rdi
0x140059da6  sub     rsp, 20h
0x140059daa  mov     eax, [rdx+4Ch]
0x140059dad  mov     rdi, rdx
0x140059db0  mov     rbx, rcx
0x140059db3  cmp     [rcx+4Ch], eax
0x140059db6  jnz     loc_140059ECD
0x140059dbc  mov     eax, [rdx+50h]
0x140059dbf  cmp     [rcx+50h], eax
0x140059dc2  jnz     loc_140059ECD
0x140059dc8  mov     eax, [rdx+54h]
0x140059dcb  cmp     [rcx+54h], eax
0x140059dce  jnz     loc_140059ECD
0x140059dd4  add     rdx, 90h; Source2
0x140059ddb  add     rcx, 90h; Source1
0x140059de2  mov     r8d, 1Ch; Length
0x140059de8  call    cs:__imp_RtlCompareMemory
0x140059def  nop     dword ptr [rax+rax+00h]
0x140059df4  cmp     rax, 1Ch
0x140059df8  jnz     loc_140059ECD
0x140059dfe  lea     rdx, [rdi+0ACh]; Source2
0x140059e05  mov     r8, rax; Length
0x140059e08  lea     rcx, [rbx+0ACh]; Source1
0x140059e0f  call    cs:__imp_RtlCompareMemory
0x140059e16  nop     dword ptr [rax+rax+00h]
0x140059e1b  cmp     rax, 1Ch
0x140059e1f  jnz     loc_140059ECD
0x140059e25  mov     eax, [rbx+80h]
0x140059e2b  cmp     eax, [rdi+80h]
0x140059e31  jnz     loc_140059ECD
0x140059e37  imul    eax, [rbx+58h]
0x140059e3b  xor     edx, edx
0x140059e3d  mov     r8, [rbx+88h]
0x140059e44  lea     rcx, [rax+rax*2]
0x140059e48  mov     eax, [rbx+54h]
0x140059e4b  div     dword ptr [rbx+50h]
0x140059e4e  lea     r10, [r8+rcx*8]
0x140059e52  lea     rdx, [rax+rax*2]
0x140059e56  mov     rax, [rdi+88h]
0x140059e5d  lea     r9, [r8+rdx*8]
0x140059e61  lea     r8, [rax+rdx*8]
0x140059e65  cmp     r9, r10
0x140059e68  jnb     short loc_140059EC9
0x140059e6a  mov     eax, [r8+0Ch]
0x140059e6e  cmp     [r9+0Ch], eax
0x140059e72  jnz     short loc_140059ECD
0x140059e74  mov     eax, [r8+10h]
0x140059e78  cmp     [r9+10h], eax
0x140059e7c  jnz     short loc_140059ECD
0x140059e7e  mov     rdx, [r9]
0x140059e81  mov     rcx, [r8]
0x140059e84  test    rdx, rdx
0x140059e87  jz      short loc_140059EBA
0x140059e89  test    rcx, rcx
0x140059e8c  jz      short loc_140059ECD
0x140059e8e  mov     eax, [rcx+10h]
0x140059e91  cmp     [rdx+10h], eax
0x140059e94  jnz     short loc_140059ECD
0x140059e96  movzx   eax, word ptr [rcx+14h]
0x140059e9a  cmp     [rdx+14h], ax
0x140059e9e  jnz     short loc_140059ECD
0x140059ea0  mov     eax, [rcx+1Ch]
0x140059ea3  cmp     [rdx+1Ch], eax
0x140059ea6  jnz     short loc_140059ECD
0x140059ea8  mov     rax, [rcx+28h]
0x140059eac  mov     rcx, [rdx+28h]
0x140059eb0  mov     rax, [rax+18h]
0x140059eb4  cmp     [rcx+18h], rax
0x140059eb8  jmp     short loc_140059EBD
0x140059eba  test    rcx, rcx
0x140059ebd  jnz     short loc_140059ECD
0x140059ebf  add     r9, 18h
0x140059ec3  add     r8, 18h
0x140059ec7  jmp     short loc_140059E65
0x140059ec9  mov     al, 1
0x140059ecb  jmp     short loc_140059ECF
0x140059ecd  xor     al, al
0x140059ecf  mov     rbx, [rsp+28h+arg_0]
0x140059ed4  add     rsp, 20h
0x140059ed8  pop     rdi
0x140059ed9  retn
```
