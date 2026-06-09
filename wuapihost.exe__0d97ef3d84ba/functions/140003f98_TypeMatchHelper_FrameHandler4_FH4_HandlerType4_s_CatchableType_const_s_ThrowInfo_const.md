# TypeMatchHelper<__FrameHandler4>(FH4::HandlerType4 *,_s_CatchableType const *,_s_ThrowInfo const *)

- ea: `0x140003f98`
- end: `0x1400040d7`
- name: `??$TypeMatchHelper@V__FrameHandler4@@@@YAHPEAUHandlerType4@FH4@@PEBU_s_CatchableType@@PEBU_s_ThrowInfo@@@Z`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140003624`

## callees

- `0x140002a80`
- `0x140002a98`
- `0x140003f98`
- `0x1400055e6`

## pseudocode

```c
__int64 __fastcall TypeMatchHelper<__FrameHandler4>(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v3; // rbx
  unsigned int v4; // edi
  __int64 v8; // rbx
  __int64 v9; // rcx
  _BYTE *v10; // rbx
  __int64 v11; // r14
  __int64 v12; // rbp
  __int64 v13; // rbx
  __int64 v14; // rbp
  __int64 v15; // rbx
  __int64 ThrowImageBase; // rax
  _BYTE *v18; // rsi

  v3 = *(int *)(a1 + 8);
  v4 = 0;
  if ( (_DWORD)v3 && v3 + GetImageBase() )
  {
    v8 = *(int *)(a1 + 8);
    v9 = (_DWORD)v8 ? v8 + GetImageBase() : 0LL;
    if ( *(_BYTE *)(v9 + 16) )
    {
      v10 = (_BYTE *)(a1 + 4);
      if ( *(char *)(a1 + 4) >= 0 || (*(_BYTE *)a2 & 0x10) == 0 )
      {
        v11 = *(int *)(a1 + 8);
        if ( (_DWORD)v11 )
          v12 = v11 + GetImageBase();
        else
          v12 = 0;
        if ( v12 != GetThrowImageBase() + *(int *)(a2 + 4) )
        {
          v13 = *(int *)(a1 + 8);
          if ( (_DWORD)v13 )
            v14 = v13 + GetImageBase();
          else
            v14 = 0;
          v15 = *(int *)(a2 + 4);
          ThrowImageBase = GetThrowImageBase();
          if ( strcmp_0((const char *)(v14 + 16), (const char *)(ThrowImageBase + v15 + 16)) )
            return 0;
          v10 = (_BYTE *)(a1 + 4);
        }
        if ( (*(_BYTE *)a2 & 2) != 0 )
        {
          if ( (*v10 & 8) == 0 )
            return v4;
          v18 = (_BYTE *)(a1 + 4);
        }
        else
        {
          v18 = v10;
        }
        if ( ((*a3 & 1) == 0 || (*v10 & 1) != 0)
          && ((*a3 & 4) == 0 || (*v10 & 4) != 0)
          && ((*a3 & 2) == 0 || (*v18 & 2) != 0) )
        {
          return 1;
        }
        return v4;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140003f98  mov     rax, rsp
0x140003f9b  mov     [rax+8], rbx
0x140003f9f  mov     [rax+10h], rbp
0x140003fa3  mov     [rax+18h], rsi
0x140003fa7  mov     [rax+20h], rdi
0x140003fab  push    r12
0x140003fad  push    r14
0x140003faf  push    r15
0x140003fb1  sub     rsp, 20h
0x140003fb5  movsxd  rbx, dword ptr [rcx+8]
0x140003fb9  xor     edi, edi
0x140003fbb  mov     r12, r8
0x140003fbe  mov     r15, rdx
0x140003fc1  mov     rsi, rcx
0x140003fc4  test    ebx, ebx
0x140003fc6  jz      loc_1400040B3
0x140003fcc  call    _GetImageBase
0x140003fd1  mov     r9, rax
0x140003fd4  add     r9, rbx
0x140003fd7  jz      loc_1400040B3
0x140003fdd  movsxd  rbx, dword ptr [rsi+8]
0x140003fe1  test    ebx, ebx
0x140003fe3  jz      short loc_140003FF0
0x140003fe5  call    _GetImageBase
0x140003fea  lea     rcx, [rbx+rax]
0x140003fee  jmp     short loc_140003FF3
0x140003ff0  mov     rcx, rdi
0x140003ff3  cmp     [rcx+10h], dil
0x140003ff7  jz      loc_1400040B3
0x140003ffd  lea     rbx, [rsi+4]
0x140004001  test    byte ptr [rbx], 80h
0x140004004  jz      short loc_140004010
0x140004006  test    byte ptr [r15], 10h
0x14000400a  jnz     loc_1400040B3
0x140004010  movsxd  r14, dword ptr [rsi+8]
0x140004014  test    r14d, r14d
0x140004017  jz      short loc_140004024
0x140004019  call    _GetImageBase
0x14000401e  lea     rbp, [r14+rax]
0x140004022  jmp     short loc_140004027
0x140004024  mov     rbp, rdi
0x140004027  call    _GetThrowImageBase
0x14000402c  movsxd  rcx, dword ptr [r15+4]
0x140004030  add     rcx, rax
0x140004033  cmp     rbp, rcx
0x140004036  jz      short loc_140004073
0x140004038  movsxd  rbx, dword ptr [rsi+8]
0x14000403c  test    ebx, ebx
0x14000403e  jz      short loc_14000404B
0x140004040  call    _GetImageBase
0x140004045  lea     rbp, [rbx+rax]
0x140004049  jmp     short loc_14000404E
0x14000404b  mov     rbp, rdi
0x14000404e  movsxd  rbx, dword ptr [r15+4]
0x140004052  call    _GetThrowImageBase
0x140004057  lea     rdx, [rbx+10h]
0x14000405b  add     rdx, rax; Str2
0x14000405e  lea     rcx, [rbp+10h]; Str1
0x140004062  call    strcmp_0
0x140004067  test    eax, eax
0x140004069  jz      short loc_14000406F
0x14000406b  xor     eax, eax
0x14000406d  jmp     short loc_1400040B8
0x14000406f  lea     rbx, [rsi+4]
0x140004073  mov     al, 2
0x140004075  test    [r15], al
0x140004078  jz      short loc_140004085
0x14000407a  test    byte ptr [rbx], 8
0x14000407d  jz      short loc_1400040AF
0x14000407f  add     rsi, 4
0x140004083  jmp     short loc_140004088
0x140004085  mov     rsi, rbx
0x140004088  test    byte ptr [r12], 1
0x14000408d  jz      short loc_140004094
0x14000408f  test    byte ptr [rbx], 1
0x140004092  jz      short loc_1400040AF
0x140004094  test    byte ptr [r12], 4
0x140004099  jz      short loc_1400040A0
0x14000409b  test    byte ptr [rbx], 4
0x14000409e  jz      short loc_1400040AF
0x1400040a0  test    [r12], al
0x1400040a4  jz      short loc_1400040AA
0x1400040a6  test    [rsi], al
0x1400040a8  jz      short loc_1400040AF
0x1400040aa  mov     edi, 1
0x1400040af  mov     eax, edi
0x1400040b1  jmp     short loc_1400040B8
0x1400040b3  mov     eax, 1
0x1400040b8  mov     rbx, [rsp+38h+arg_0]
0x1400040bd  mov     rbp, [rsp+38h+arg_8]
0x1400040c2  mov     rsi, [rsp+38h+arg_10]
0x1400040c7  mov     rdi, [rsp+38h+arg_18]
0x1400040cc  add     rsp, 20h
0x1400040d0  pop     r15
0x1400040d2  pop     r14
0x1400040d4  pop     r12
0x1400040d6  retn
```
