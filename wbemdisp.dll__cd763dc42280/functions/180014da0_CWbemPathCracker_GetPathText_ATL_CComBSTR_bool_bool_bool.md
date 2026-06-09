# CWbemPathCracker::GetPathText(ATL::CComBSTR &,bool,bool,bool)

- ea: `0x180014da0`
- end: `0x180014ede`
- name: `?GetPathText@CWbemPathCracker@@QEAA_NAEAVCComBSTR@ATL@@_N11@Z`
- size: `318`
- prototype: `bool __fastcall(CWbemPathCracker *__hidden this, struct ATL::CComBSTR *, bool, bool, bool)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002e7a0`
- `0x18002ecd0`
- `0x18002edf0`
- `0x180032bac`

## callees

- `0x180014da0`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180014e5e`
- `OLEAUT32!__imp_SysAllocString` at `0x180014eb7`
- `OLEAUT32!__imp_SysAllocString` at `0x180014e5e`
- `OLEAUT32!__imp_SysAllocString` at `0x180014eb7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014e23`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180014e23`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014e79`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180014e79`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall CWbemPathCracker::GetPathText(
        CWbemPathCracker *this,
        struct ATL::CComBSTR *a2,
        char a3,
        char a4,
        bool a5)
{
  bool v7; // di
  __int64 v8; // rcx
  unsigned int v9; // ebp
  OLECHAR *v10; // rax
  OLECHAR *v11; // rsi
  BSTR v12; // rax
  BSTR v14; // rax
  int v15; // [rsp+50h] [rbp+8h] BYREF

  v7 = 0;
  if ( *((_DWORD *)this + 7) != 1 )
    return v7;
  v8 = *((_QWORD *)this + 1);
  if ( !v8 )
    return v7;
  if ( a4 )
  {
    v9 = 4;
  }
  else if ( a3 )
  {
    v9 = 2;
  }
  else
  {
    v9 = 0;
    if ( a5 )
      v9 = 16;
  }
  v15 = 0;
  (*(void (__fastcall **)(__int64, _QWORD, int *, _QWORD))(*(_QWORD *)v8 + 32LL))(v8, v9, &v15, 0);
  if ( v15 )
  {
    v10 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v15 + 1), 2u));
    v11 = v10;
    if ( v10 )
    {
      v10[v15] = 0;
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, int *, OLECHAR *))(**((_QWORD **)this + 1) + 32LL))(
             *((_QWORD *)this + 1),
             v9,
             &v15,
             v10) >= 0 )
      {
        v12 = SysAllocString(v11);
        *(_QWORD *)a2 = v12;
        v7 = v12 != 0;
      }
      CWin32DefaultArena::WbemMemFree(v11);
    }
    return v7;
  }
  v14 = SysAllocString(&SystemName);
  *(_QWORD *)a2 = v14;
  return v14 != 0;
}

```

## disassembly

```asm
0x180014da0  mov     [rsp+arg_8], rbx
0x180014da5  mov     [rsp+arg_10], rbp
0x180014daa  push    rsi
0x180014dab  push    rdi
0x180014dac  push    r14
0x180014dae  sub     rsp, 30h
0x180014db2  mov     r14, rdx
0x180014db5  mov     rbx, rcx
0x180014db8  xor     dil, dil
0x180014dbb  cmp     dword ptr [rcx+1Ch], 1
0x180014dbf  jnz     loc_180014E80
0x180014dc5  mov     rcx, [rcx+8]
0x180014dc9  test    rcx, rcx
0x180014dcc  jz      loc_180014E80
0x180014dd2  test    r9b, r9b
0x180014dd5  jz      loc_180014E97
0x180014ddb  mov     ebp, 4
0x180014de0  mov     [rsp+48h+arg_0], 0
0x180014de8  mov     rdx, [rcx]
0x180014deb  mov     rax, [rdx+20h]
0x180014def  xor     r9d, r9d
0x180014df2  lea     r8, [rsp+48h+arg_0]
0x180014df7  mov     edx, ebp
0x180014df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dfe  mov     ecx, [rsp+48h+arg_0]
0x180014e02  test    ecx, ecx
0x180014e04  jz      loc_180014EB0
0x180014e0a  lea     edx, [rcx+1]
0x180014e0d  mov     eax, 2
0x180014e12  mul     rdx
0x180014e15  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180014e1c  cmovb   rax, rcx
0x180014e20  mov     rcx, rax
0x180014e23  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180014e29  mov     rsi, rax
0x180014e2c  test    rax, rax
0x180014e2f  jz      short loc_180014E80
0x180014e31  mov     r8d, [rsp+48h+arg_0]
0x180014e36  xor     ecx, ecx
0x180014e38  mov     [rax+r8*2], cx
0x180014e3d  mov     rcx, [rbx+8]
0x180014e41  mov     r8, [rcx]
0x180014e44  mov     rax, [r8+20h]
0x180014e48  mov     r9, rsi
0x180014e4b  lea     r8, [rsp+48h+arg_0]
0x180014e50  mov     edx, ebp
0x180014e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e57  test    eax, eax
0x180014e59  js      short loc_180014E76
0x180014e5b  mov     rcx, rsi; psz
0x180014e5e  call    cs:__imp_SysAllocString
0x180014e64  mov     [r14], rax
0x180014e67  movzx   edi, dil
0x180014e6b  mov     edx, 1
0x180014e70  test    rax, rax
0x180014e73  cmovnz  edi, edx
0x180014e76  mov     rcx, rsi
0x180014e79  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180014e7f  nop
0x180014e80  movzx   eax, dil
0x180014e84  mov     rbx, [rsp+48h+arg_8]
0x180014e89  mov     rbp, [rsp+48h+arg_10]
0x180014e8e  add     rsp, 30h
0x180014e92  pop     r14
0x180014e94  pop     rdi
0x180014e95  pop     rsi
0x180014e96  retn
0x180014e97  test    r8b, r8b
0x180014e9a  jnz     short loc_180014ED4
0x180014e9c  xor     ebp, ebp
0x180014e9e  mov     eax, 10h
0x180014ea3  cmp     [rsp+48h+arg_20], dil
0x180014ea8  cmovnz  ebp, eax
0x180014eab  jmp     loc_180014DE0
0x180014eb0  lea     rcx, SystemName; psz
0x180014eb7  call    cs:__imp_SysAllocString
0x180014ebd  mov     [r14], rax
0x180014ec0  movzx   ecx, dil
0x180014ec4  mov     edx, 1
0x180014ec9  test    rax, rax
0x180014ecc  cmovnz  ecx, edx
0x180014ecf  movzx   eax, cl
0x180014ed2  jmp     short loc_180014E84
0x180014ed4  mov     ebp, 2
0x180014ed9  jmp     loc_180014DE0
```
