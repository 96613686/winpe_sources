# CRegistry::Subkey(ulong)

- ea: `0x180014440`
- end: `0x18001470f`
- name: `?Subkey@CRegistry@@QEAAPEBGK@Z`
- size: `719`
- prototype: `const unsigned __int16 *(CRegistry *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x18002a528`
- `0x18002ad8c`

## callees

- `0x180014440`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180014513`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180014513`

## pseudocode

```c
const unsigned __int16 *__fastcall CRegistry::Subkey(CRegistry *this, DWORD a2)
{
  ulong v2; // eax
  void *v5; // rdi
  void *v6; // rcx
  void **v7; // r14
  int v8; // edi
  const WCHAR *v9; // rsi
  unsigned int v10; // ecx
  WCHAR *v11; // r8
  LSTATUS v12; // eax
  DWORD v14; // edi
  DWORD v15; // eax
  void *v16; // rsi
  void *v17; // rcx
  DWORD v18; // ebp
  void *v19; // r15
  void *v20; // rax
  DWORD cchName; // [rsp+80h] [rbp+8h] BYREF
  ulong pExceptionObject; // [rsp+90h] [rbp+18h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+98h] [rbp+20h] BYREF

  v2 = *((_DWORD *)this + 10);
  cchName = 0;
  ftLastWriteTime = 0;
  if ( v2 )
  {
    pExceptionObject = v2;
    throw &pExceptionObject;
  }
  if ( *((_DWORD *)this + 9) >= 0x80u )
  {
    v7 = (void **)((char *)this + 24);
  }
  else
  {
    v5 = operator new[](0x80u);
    if ( !v5 )
    {
      pExceptionObject = 14;
      throw &pExceptionObject;
    }
    v6 = (void *)*((_QWORD *)this + 3);
    v7 = (void **)((char *)this + 24);
    if ( v6 )
      operator delete(v6);
    *v7 = v5;
    *((_DWORD *)this + 9) = 128;
  }
  v8 = 0;
  v9 = 0;
LABEL_8:
  *((_DWORD *)this + 8) = 0;
  while ( !v8 )
  {
    v10 = *((_DWORD *)this + 9);
    cchName = v10 >> 1;
    if ( v10 )
      v11 = (WCHAR *)*((_QWORD *)this + 3);
    else
      v11 = (WCHAR *)&WideCharStr;
    v12 = RegEnumKeyExW(*(HKEY *)this, a2, v11, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( v12 == 259 )
    {
      v9 = 0;
      v8 = 1;
    }
    else
    {
      if ( v12 )
      {
        if ( v12 != 234 )
        {
          pExceptionObject = v12;
          throw &pExceptionObject;
        }
        v18 = 2 * cchName + 2;
        if ( *((_DWORD *)this + 9) < v18 )
        {
          v19 = operator new[](v18);
          if ( !v19 )
          {
            pExceptionObject = 14;
            throw &pExceptionObject;
          }
          if ( *v7 )
            operator delete(*v7);
          *v7 = v19;
          *((_DWORD *)this + 9) = v18;
        }
        goto LABEL_8;
      }
      v14 = 2 * cchName + 2;
      v15 = *((_DWORD *)this + 9);
      if ( !*((_DWORD *)this + 8) )
      {
        if ( v15 >= v14 )
          goto LABEL_22;
        v16 = operator new[](v14);
        if ( !v16 )
        {
          pExceptionObject = 14;
          throw &pExceptionObject;
        }
        v17 = *v7;
        if ( *v7 )
LABEL_20:
          operator delete(v17);
        v15 = v14;
        *((_DWORD *)this + 9) = v14;
        *v7 = v16;
        goto LABEL_22;
      }
      if ( v15 < v14 )
      {
        v20 = operator new[](v14);
        v16 = v20;
        if ( !v20 )
        {
          pExceptionObject = 14;
          throw &pExceptionObject;
        }
        memcpy_0(v20, *v7, *((unsigned int *)this + 8));
        v17 = *v7;
        goto LABEL_20;
      }
LABEL_22:
      *((_DWORD *)this + 8) = v14;
      if ( v15 )
        v9 = (const WCHAR *)*v7;
      else
        v9 = &WideCharStr;
      v8 = 1;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180014440  mov     r11, rsp
0x180014443  push    rbx
0x180014444  push    r12
0x180014446  push    r13
0x180014448  sub     rsp, 60h
0x18001444c  mov     eax, [rcx+28h]
0x18001444f  xor     r13d, r13d
0x180014452  mov     [r11+8], r13d
0x180014456  mov     r12d, edx
0x180014459  mov     [r11+20h], r13
0x18001445d  mov     rbx, rcx
0x180014460  test    eax, eax
0x180014462  jnz     loc_180014657
0x180014468  cmp     dword ptr [rcx+24h], 80h
0x18001446f  mov     [r11-28h], rdi
0x180014473  mov     [r11-30h], r14
0x180014477  jnb     loc_180014603
0x18001447d  mov     ecx, 80h; unsigned __int64
0x180014482  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014487  mov     rdi, rax
0x18001448a  test    rax, rax
0x18001448d  jz      loc_180014673
0x180014493  mov     rcx, [rbx+18h]; void *
0x180014497  lea     r14, [rbx+18h]
0x18001449b  test    rcx, rcx
0x18001449e  jz      short loc_1800144A5
0x1800144a0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800144a5  mov     [r14], rdi
0x1800144a8  mov     dword ptr [rbx+24h], 80h
0x1800144af  mov     [rsp+78h+var_20], rsi
0x1800144b4  mov     edi, r13d
0x1800144b7  mov     [rsp+78h+arg_8], rbp
0x1800144bf  mov     rsi, r13
0x1800144c2  mov     [rsp+78h+var_38], r15
0x1800144c7  mov     [rbx+20h], r13d
0x1800144cb  test    edi, edi
0x1800144cd  jnz     short loc_18001452A
0x1800144cf  mov     ecx, [rbx+24h]
0x1800144d2  mov     eax, ecx
0x1800144d4  shr     eax, 1
0x1800144d6  mov     [rsp+78h+cchName], eax
0x1800144dd  test    ecx, ecx
0x1800144df  jz      loc_18001460C
0x1800144e5  mov     r8, [rbx+18h]; lpName
0x1800144e9  mov     rcx, [rbx]; hKey
0x1800144ec  lea     rax, [rsp+78h+ftLastWriteTime]
0x1800144f4  mov     [rsp+78h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800144f9  lea     r9, [rsp+78h+cchName]; lpcchName
0x180014501  mov     [rsp+78h+lpcchClass], r13; lpcchClass
0x180014506  mov     edx, r12d; dwIndex
0x180014509  mov     [rsp+78h+lpClass], r13; lpClass
0x18001450e  mov     [rsp+78h+lpReserved], r13; lpReserved
0x180014513  call    cs:__imp_RegEnumKeyExW
0x180014519  cmp     eax, 103h
0x18001451e  jnz     short loc_180014553
0x180014520  mov     rsi, r13
0x180014523  mov     edi, 1
0x180014528  jmp     short loc_1800144CB
0x18001452a  mov     rbp, [rsp+78h+arg_8]
0x180014532  mov     rax, rsi
0x180014535  mov     rsi, [rsp+78h+var_20]
0x18001453a  mov     r15, [rsp+78h+var_38]
0x18001453f  mov     rdi, [rsp+78h+var_28]
0x180014544  mov     r14, [rsp+78h+var_30]
0x180014549  add     rsp, 60h
0x18001454d  pop     r13
0x18001454f  pop     r12
0x180014551  pop     rbx
0x180014552  retn
0x180014553  test    eax, eax
0x180014555  jnz     short loc_1800145B6
0x180014557  mov     eax, [rsp+78h+cchName]
0x18001455e  lea     edi, ds:2[rax*2]
0x180014565  mov     eax, [rbx+24h]
0x180014568  cmp     [rbx+20h], r13d
0x18001456c  ja      loc_180014618
0x180014572  cmp     eax, edi
0x180014574  jnb     short loc_18001459E
0x180014576  mov     ecx, edi; unsigned __int64
0x180014578  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001457d  mov     rsi, rax
0x180014580  test    rax, rax
0x180014583  jz      loc_1800146EF
0x180014589  mov     rcx, [r14]; void *
0x18001458c  test    rcx, rcx
0x18001458f  jz      short loc_180014596
0x180014591  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014596  mov     eax, edi
0x180014598  mov     [rbx+24h], edi
0x18001459b  mov     [r14], rsi
0x18001459e  mov     [rbx+20h], edi
0x1800145a1  test    eax, eax
0x1800145a3  jz      loc_180014646
0x1800145a9  mov     rsi, [r14]
0x1800145ac  mov     edi, 1
0x1800145b1  jmp     loc_1800144CB
0x1800145b6  cmp     eax, 0EAh
0x1800145bb  jnz     loc_1800146B3
0x1800145c1  mov     eax, [rsp+78h+cchName]
0x1800145c8  lea     ebp, ds:2[rax*2]
0x1800145cf  cmp     [rbx+24h], ebp
0x1800145d2  jnb     loc_1800144C7
0x1800145d8  mov     ecx, ebp; unsigned __int64
0x1800145da  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800145df  mov     r15, rax
0x1800145e2  test    rax, rax
0x1800145e5  jz      loc_180014693
0x1800145eb  mov     rcx, [r14]; void *
0x1800145ee  test    rcx, rcx
0x1800145f1  jz      short loc_1800145F8
0x1800145f3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800145f8  mov     [r14], r15
0x1800145fb  mov     [rbx+24h], ebp
0x1800145fe  jmp     loc_1800144C7
0x180014603  lea     r14, [rcx+18h]
0x180014607  jmp     loc_1800144AF
0x18001460c  lea     r8, WideCharStr
0x180014613  jmp     loc_1800144E9
0x180014618  cmp     eax, edi
0x18001461a  jnb     short loc_18001459E
0x18001461c  mov     ecx, edi; unsigned __int64
0x18001461e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014623  mov     rsi, rax
0x180014626  test    rax, rax
0x180014629  jz      loc_1800146CF
0x18001462f  mov     r8d, [rbx+20h]; Size
0x180014633  mov     rcx, rax; void *
0x180014636  mov     rdx, [r14]; Src
0x180014639  call    memcpy_0
0x18001463e  mov     rcx, [r14]
0x180014641  jmp     loc_180014591
0x180014646  lea     rsi, WideCharStr
0x18001464d  mov     edi, 1
0x180014652  jmp     loc_1800144CB
0x180014657  lea     rdx, _TI1K; pThrowInfo
0x18001465e  mov     [rsp+78h+pExceptionObject], eax
0x180014665  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001466d  call    _CxxThrowException_0
0x180014673  lea     rdx, _TI1K; pThrowInfo
0x18001467a  mov     [rsp+78h+pExceptionObject], 0Eh
0x180014685  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18001468d  call    _CxxThrowException_0
0x180014693  lea     rdx, _TI1K; pThrowInfo
0x18001469a  mov     [rsp+78h+pExceptionObject], 0Eh
0x1800146a5  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800146ad  call    _CxxThrowException_0
0x1800146b3  lea     rdx, _TI1K; pThrowInfo
0x1800146ba  mov     [rsp+78h+pExceptionObject], eax
0x1800146c1  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800146c9  call    _CxxThrowException_0
0x1800146cf  lea     rdx, _TI1K; pThrowInfo
0x1800146d6  mov     [rsp+78h+pExceptionObject], 0Eh
0x1800146e1  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800146e9  call    _CxxThrowException_0
0x1800146ef  lea     rdx, _TI1K; pThrowInfo
0x1800146f6  mov     [rsp+78h+pExceptionObject], 0Eh
0x180014701  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180014709  call    _CxxThrowException_0
```
