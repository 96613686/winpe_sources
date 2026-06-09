# SetProxyBlanketImpersonationLevel(IUnknown *,ulong,int *)

- ea: `0x14000bb94`
- end: `0x14000bd72`
- name: `?SetProxyBlanketImpersonationLevel@@YAJPEAUIUnknown@@KPEAH@Z`
- size: `478`
- prototype: `__int64 __fastcall(struct IUnknown *, __int64, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005e60`
- `0x1400080bc`
- `0x14000d308`

## callees

- `0x140002ac0`
- `0x14000bb94`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bc4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bd28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bc4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000bd28`

## string_xrefs

- `0x14000bd0f`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetProxyBlanketImpersonationLevel(struct IUnknown *a1, __int64 a2, int *a3)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  int v6; // eax
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  LPVOID *p_pv; // [rsp+20h] [rbp-29h]
  LPVOID pv; // [rsp+60h] [rbp+17h] BYREF
  int v13; // [rsp+68h] [rbp+1Fh]
  unsigned int v14; // [rsp+6Ch] [rbp+23h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+27h] BYREF
  __int64 v16; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v16 = 0;
  pv = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  if ( !a1 )
  {
    v4 = -2147467261;
    v5 = 27;
LABEL_6:
    v7 = v4;
    v8 = v5;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      (const char *)v7,
      (int)p_pv);
    goto LABEL_14;
  }
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_0000013d_0000_0000_c000_000000000046,
         &v16);
  v4 = v6;
  if ( v6 >= 0 )
  {
    p_pv = &pv;
    v9 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, unsigned int *, unsigned int *))(*(_QWORD *)v16 + 24LL))(
           v16,
           a1,
           &v15,
           &v14);
    v4 = v9;
    if ( v9 >= 0 )
    {
      LODWORD(p_pv) = (_DWORD)pv;
      v9 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, _QWORD, _QWORD))(*(_QWORD *)v16 + 32LL))(
             v16,
             a1,
             v15,
             v14);
      v4 = v9;
      if ( v9 >= 0 )
        goto LABEL_13;
      v8 = 69;
    }
    else
    {
      v8 = 55;
    }
    v7 = (unsigned int)v9;
    goto LABEL_12;
  }
  if ( v6 != -2147467262 )
  {
    v5 = 32;
    goto LABEL_6;
  }
LABEL_13:
  v4 = 0;
LABEL_14:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return v4;
}

```

## disassembly

```asm
0x14000bb94  mov     [rsp-8+arg_10], rbx
0x14000bb99  mov     [rsp-8+arg_18], rsi
0x14000bb9e  push    rbp
0x14000bb9f  push    rdi
0x14000bba0  push    r14
0x14000bba2  lea     rbp, [rsp-47h]
0x14000bba7  sub     rsp, 90h
0x14000bbae  mov     rax, cs:__security_cookie
0x14000bbb5  xor     rax, rsp
0x14000bbb8  mov     [rbp+57h+var_20], rax
0x14000bbbc  mov     r14d, edx
0x14000bbbf  mov     rdi, rcx
0x14000bbc2  mov     [rbp+57h+var_50], 0
0x14000bbca  mov     [rbp+57h+var_28], 0
0x14000bbd2  mov     [rbp+57h+pv], 0
0x14000bbda  mov     [rbp+57h+var_30], 0
0x14000bbe1  mov     [rbp+57h+var_34], 0
0x14000bbe8  mov     [rbp+57h+var_38], 0
0x14000bbef  mov     [rbp+57h+var_48], 0
0x14000bbf6  test    rcx, rcx
0x14000bbf9  jnz     short loc_14000BC05
0x14000bbfb  mov     ebx, 80004003h
0x14000bc00  lea     eax, [rcx+1Bh]
0x14000bc03  jmp     short loc_14000BC31
0x14000bc05  mov     rax, [rcx]
0x14000bc08  lea     r8, [rbp+57h+var_28]
0x14000bc0c  lea     rdx, _GUID_0000013d_0000_0000_c000_000000000046
0x14000bc13  mov     rax, [rax]
0x14000bc16  call    _guard_dispatch_icall
0x14000bc1b  mov     ebx, eax
0x14000bc1d  test    eax, eax
0x14000bc1f  jns     short loc_14000BC3B
0x14000bc21  cmp     eax, 80004002h
0x14000bc26  jz      loc_14000BD1D
0x14000bc2c  mov     eax, 20h ; ' '
0x14000bc31  mov     r9d, ebx
0x14000bc34  mov     edx, eax
0x14000bc36  jmp     loc_14000BD0B
0x14000bc3b  mov     rbx, [rbp+57h+var_28]
0x14000bc3f  mov     rax, [rbx]
0x14000bc42  mov     rsi, [rax+18h]
0x14000bc46  mov     rcx, [rbp+57h+pv]; pv
0x14000bc4a  test    rcx, rcx
0x14000bc4d  jz      short loc_14000BC5D
0x14000bc4f  call    cs:__imp_CoTaskMemFree
0x14000bc55  mov     [rbp+57h+pv], 0
0x14000bc5d  lea     rax, [rbp+57h+var_48]
0x14000bc61  mov     [rsp+0A0h+var_60], rax
0x14000bc66  lea     rax, [rbp+57h+var_50]
0x14000bc6a  mov     [rsp+0A0h+var_68], rax
0x14000bc6f  mov     [rsp+0A0h+var_70], 0
0x14000bc78  lea     rax, [rbp+57h+var_38]
0x14000bc7c  mov     [rsp+0A0h+var_78], rax
0x14000bc81  lea     rax, [rbp+57h+pv]
0x14000bc85  mov     qword ptr [rsp+0A0h+var_80], rax
0x14000bc8a  lea     r9, [rbp+57h+var_34]
0x14000bc8e  lea     r8, [rbp+57h+var_30]
0x14000bc92  mov     rdx, rdi
0x14000bc95  mov     rcx, rbx
0x14000bc98  mov     rax, rsi
0x14000bc9b  call    _guard_dispatch_icall
0x14000bca0  mov     ebx, eax
0x14000bca2  test    eax, eax
0x14000bca4  jns     short loc_14000BCAD
0x14000bca6  mov     edx, 37h ; '7'
0x14000bcab  jmp     short loc_14000BD08
0x14000bcad  mov     r8d, [rbp+57h+var_48]
0x14000bcb1  and     r8d, 0FFFFFFBFh
0x14000bcb5  or      r8d, 20h
0x14000bcb9  mov     [rbp+57h+var_48], r8d
0x14000bcbd  mov     r10, [rbp+57h+var_50]
0x14000bcc1  mov     r11d, [rbp+57h+var_38]
0x14000bcc5  mov     rbx, [rbp+57h+pv]
0x14000bcc9  mov     rcx, [rbp+57h+var_28]
0x14000bccd  mov     rax, [rcx]
0x14000bcd0  mov     dword ptr [rsp+0A0h+var_60], r8d
0x14000bcd5  mov     [rsp+0A0h+var_68], r10
0x14000bcda  mov     dword ptr [rsp+0A0h+var_70], r14d
0x14000bcdf  mov     dword ptr [rsp+0A0h+var_78], r11d
0x14000bce4  mov     qword ptr [rsp+0A0h+var_80], rbx; int
0x14000bce9  mov     r9d, [rbp+57h+var_34]
0x14000bced  mov     r8d, [rbp+57h+var_30]
0x14000bcf1  mov     rdx, rdi
0x14000bcf4  mov     rax, [rax+20h]
0x14000bcf8  call    _guard_dispatch_icall
0x14000bcfd  mov     ebx, eax
0x14000bcff  test    eax, eax
0x14000bd01  jns     short loc_14000BD1D
0x14000bd03  mov     edx, 45h ; 'E'; void *
0x14000bd08  mov     r9d, eax; char *
0x14000bd0b  mov     rcx, [rbp+5Fh]; this
0x14000bd0f  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000bd16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bd1b  jmp     short loc_14000BD1F
0x14000bd1d  xor     ebx, ebx
0x14000bd1f  mov     rcx, [rbp+57h+pv]; pv
0x14000bd23  test    rcx, rcx
0x14000bd26  jz      short loc_14000BD36
0x14000bd28  call    cs:__imp_CoTaskMemFree
0x14000bd2e  mov     [rbp+57h+pv], 0
0x14000bd36  mov     rcx, [rbp+57h+var_28]
0x14000bd3a  test    rcx, rcx
0x14000bd3d  jz      short loc_14000BD4C
0x14000bd3f  mov     rdx, [rcx]
0x14000bd42  mov     rax, [rdx+10h]
0x14000bd46  call    _guard_dispatch_icall
0x14000bd4b  nop
0x14000bd4c  mov     eax, ebx
0x14000bd4e  mov     rcx, [rbp+57h+var_20]
0x14000bd52  xor     rcx, rsp; StackCookie
0x14000bd55  call    __security_check_cookie
0x14000bd5a  lea     r11, [rsp+0A0h+var_10]
0x14000bd62  mov     rbx, [r11+30h]
0x14000bd66  mov     rsi, [r11+38h]
0x14000bd6a  mov     rsp, r11
0x14000bd6d  pop     r14
0x14000bd6f  pop     rdi
0x14000bd70  pop     rbp
0x14000bd71  retn
```
