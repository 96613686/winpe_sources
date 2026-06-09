# _ContactToMapi_Gender

- ea: `0x180010580`
- end: `0x1800106fc`
- name: `_ContactToMapi_Gender`
- size: `380`
- prototype: `__int64 __fastcall(struct IContactProperties *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180006f7c`
- `0x180008f74`
- `0x180010580`
- `0x180013be0`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180010632`
- `KERNEL32!CompareStringW` at `0x18001066e`
- `KERNEL32!CompareStringW` at `0x1800106aa`
- `KERNEL32!CompareStringW` at `0x180010632`
- `KERNEL32!CompareStringW` at `0x18001066e`
- `KERNEL32!CompareStringW` at `0x1800106aa`

## pseudocode

```c
__int64 __fastcall ContactToMapi_Gender(struct IContactProperties *a1, __int64 a2, __int64 a3)
{
  int StringFromIProperties; // eax
  unsigned int v7; // edi
  int v8; // eax
  const WCHAR *v9; // rdi
  const WCHAR *v10; // r8
  PCNZWCH v11; // rbp
  const WCHAR *v12; // r8
  int v14; // [rsp+30h] [rbp-278h] BYREF
  PCNZWCH lpString1[3]; // [rsp+38h] [rbp-270h] BYREF
  unsigned __int16 v16[264]; // [rsp+50h] [rbp-258h] BYREF

  STRW::STRW((STRW *)&v14, v16, 0x104u);
  *(_DWORD *)a2 = 10;
  StringFromIProperties = GetStringFromIProperties(a1, *(const unsigned __int16 **)(a3 + 32), (struct STRW *)&v14);
  v7 = StringFromIProperties;
  if ( StringFromIProperties != -2147024893 )
  {
    if ( StringFromIProperties < 0 )
      goto LABEL_17;
    v8 = *(_DWORD *)(a3 + 24);
    v9 = &Str;
    v10 = &Str;
    v11 = lpString1[0];
    if ( v14 )
      v10 = lpString1[0];
    *(_DWORD *)a2 = v8;
    if ( CompareStringW(0x7Fu, 1u, v10, -1, L"Unspecified", -1) == 2 )
    {
      *(_WORD *)(a2 + 8) = 0;
    }
    else
    {
      v12 = &Str;
      if ( v14 )
        v12 = v11;
      if ( CompareStringW(0x7Fu, 1u, v12, -1, L"Female", -1) == 2 )
      {
        *(_WORD *)(a2 + 8) = 1;
      }
      else
      {
        if ( v14 )
          v9 = v11;
        if ( CompareStringW(0x7Fu, 1u, v9, -1, L"Male", -1) != 2 )
        {
          *(_DWORD *)a2 = 10;
          v7 = -2147418113;
          goto LABEL_17;
        }
        *(_WORD *)(a2 + 8) = 2;
      }
    }
  }
  v7 = 0;
LABEL_17:
  v14 = 0;
  BUFFER::ReleaseStorage((BUFFER *)lpString1);
  return v7;
}

```

## disassembly

```asm
0x180010580  push    rbx
0x180010582  push    rbp
0x180010583  push    rsi
0x180010584  push    rdi
0x180010585  push    r12
0x180010587  push    r13
0x180010589  push    r15
0x18001058b  sub     rsp, 270h
0x180010592  mov     rax, cs:__security_cookie
0x180010599  xor     rax, rsp
0x18001059c  mov     [rsp+2A8h+var_48], rax
0x1800105a4  mov     rbp, r8
0x1800105a7  mov     rbx, rcx
0x1800105aa  mov     rsi, rdx
0x1800105ad  lea     rcx, [rsp+2A8h+var_278]; this
0x1800105b2  mov     r8d, 104h; unsigned int
0x1800105b8  lea     rdx, [rsp+2A8h+var_258]; unsigned __int16 *
0x1800105bd  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x1800105c2  mov     dword ptr [rsi], 0Ah
0x1800105c8  lea     r8, [rsp+2A8h+var_278]; struct STRW *
0x1800105cd  mov     rdx, [rbp+20h]; unsigned __int16 *
0x1800105d1  mov     rcx, rbx; struct IContactProperties *
0x1800105d4  call    ?GetStringFromIProperties@@YAJPEAUIContactProperties@@PEBGPEAVSTRW@@@Z; GetStringFromIProperties(IContactProperties *,ushort const *,STRW *)
0x1800105d9  xor     ebx, ebx
0x1800105db  mov     edi, eax
0x1800105dd  cmp     eax, 80070003h
0x1800105e2  jnz     short loc_1800105EB
0x1800105e4  mov     edi, ebx
0x1800105e6  jmp     loc_1800106CA
0x1800105eb  test    eax, eax
0x1800105ed  js      loc_1800106CA
0x1800105f3  mov     eax, [rbp+18h]
0x1800105f6  lea     rdi, Str
0x1800105fd  cmp     [rsp+2A8h+var_278], ebx
0x180010601  mov     r8, rdi
0x180010604  mov     rbp, [rsp+2A8h+lpString1]
0x180010609  cmovnz  r8, rbp; lpString1
0x18001060d  mov     [rsi], eax
0x18001060f  or      r13d, 0FFFFFFFFh
0x180010613  lea     rax, String2; "Unspecified"
0x18001061a  mov     [rsp+2A8h+cchCount2], r13d; cchCount2
0x18001061f  mov     r9d, r13d; cchCount1
0x180010622  mov     [rsp+2A8h+lpString2], rax; lpString2
0x180010627  lea     r15d, [r13+2]
0x18001062b  mov     edx, r15d; dwCmpFlags
0x18001062e  lea     ecx, [r15+7Eh]; Locale
0x180010632  call    cs:__imp_CompareStringW
0x180010638  lea     r12d, [r13+3]
0x18001063c  cmp     eax, r12d
0x18001063f  jnz     short loc_180010647
0x180010641  mov     [rsi+8], bx
0x180010645  jmp     short loc_1800105E4
0x180010647  cmp     [rsp+2A8h+var_278], ebx
0x18001064b  lea     rax, aFemale; "Female"
0x180010652  mov     r8, rdi
0x180010655  mov     [rsp+2A8h+cchCount2], r13d; cchCount2
0x18001065a  cmovnz  r8, rbp; lpString1
0x18001065e  mov     [rsp+2A8h+lpString2], rax; lpString2
0x180010663  mov     r9d, r13d; cchCount1
0x180010666  mov     edx, r15d; dwCmpFlags
0x180010669  mov     ecx, 7Fh; Locale
0x18001066e  call    cs:__imp_CompareStringW
0x180010674  cmp     eax, r12d
0x180010677  jnz     short loc_180010683
0x180010679  mov     [rsi+8], r15w
0x18001067e  jmp     loc_1800105E4
0x180010683  cmp     [rsp+2A8h+var_278], ebx
0x180010687  lea     rax, aMale; "Male"
0x18001068e  mov     [rsp+2A8h+cchCount2], r13d; cchCount2
0x180010693  mov     r9d, r13d; cchCount1
0x180010696  cmovnz  rdi, rbp
0x18001069a  mov     [rsp+2A8h+lpString2], rax; lpString2
0x18001069f  mov     r8, rdi; lpString1
0x1800106a2  mov     edx, r15d; dwCmpFlags
0x1800106a5  mov     ecx, 7Fh; Locale
0x1800106aa  call    cs:__imp_CompareStringW
0x1800106b0  cmp     eax, r12d
0x1800106b3  jnz     short loc_1800106BF
0x1800106b5  mov     [rsi+8], r12w
0x1800106ba  jmp     loc_1800105E4
0x1800106bf  mov     dword ptr [rsi], 0Ah
0x1800106c5  mov     edi, 8000FFFFh
0x1800106ca  lea     rcx, [rsp+2A8h+lpString1]; this
0x1800106cf  mov     [rsp+2A8h+var_278], ebx
0x1800106d3  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x1800106d8  mov     eax, edi
0x1800106da  mov     rcx, [rsp+2A8h+var_48]
0x1800106e2  xor     rcx, rsp; StackCookie
0x1800106e5  call    __security_check_cookie
0x1800106ea  add     rsp, 270h
0x1800106f1  pop     r15
0x1800106f3  pop     r13
0x1800106f5  pop     r12
0x1800106f7  pop     rdi
0x1800106f8  pop     rsi
0x1800106f9  pop     rbp
0x1800106fa  pop     rbx
0x1800106fb  retn
```
