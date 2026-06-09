# RunUpdateDeploymentSession(wchar_t const *,HINSTANCE__ *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x1400066b0`
- end: `0x1400068f7`
- name: `?RunUpdateDeploymentSession@@YAJPEB_WPEAUHINSTANCE__@@0000@Z`
- size: `583`
- prototype: `int(const wchar_t *, HINSTANCE, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400080bc`

## callees

- `0x140002ac0`
- `0x140003e74`
- `0x1400066b0`
- `0x14000bda4`
- `0x14001aa3c`
- `0x14001aa60`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400067a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400067a2`
- `RPCRT4!UuidFromStringW` at `0x1400067d1`
- `RPCRT4!UuidFromStringW` at `0x1400067d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall RunUpdateDeploymentSession(
        const wchar_t *a1,
        HINSTANCE a2,
        wchar_t *a3,
        const wchar_t *a4,
        wchar_t *String,
        wchar_t *a6)
{
  __int64 v9; // rdx
  unsigned __int64 v10; // r12
  int v11; // r13d
  FARPROC ProcAddress; // rdi
  const char *v13; // r9
  unsigned int LastError; // ebx
  RPC_STATUS v15; // eax
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  int v20; // [rsp+20h] [rbp-59h]
  UUID v21; // [rsp+40h] [rbp-39h] BYREF
  __int64 v22; // [rsp+50h] [rbp-29h] BYREF
  UUID Uuid; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  if ( !a1 || !*a1 )
  {
    v9 = 21;
    goto LABEL_34;
  }
  if ( !a2 )
  {
    v9 = 22;
LABEL_34:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\SessionHost.cpp",
      (const char *)0x80070057LL,
      v20);
    return LastError;
  }
  if ( !a3 || !*a3 )
  {
    v9 = 23;
    goto LABEL_34;
  }
  if ( !a4 || !*a4 )
  {
    v9 = 24;
    goto LABEL_34;
  }
  if ( !String || !*String )
  {
    v9 = 25;
    goto LABEL_34;
  }
  if ( !a6 || !*a6 )
  {
    v9 = 26;
    goto LABEL_34;
  }
  Uuid = GUID_NULL;
  v22 = 0;
  v10 = o_wcstoull_0(a4, 0, 10);
  v11 = o_wcstoull_0(String, 0, 10);
  o_wcstoull_0(a6, 0, 10);
  ProcAddress = GetProcAddress(a2, (LPCSTR)4);
  if ( !ProcAddress )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x25,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\SessionHost.cpp",
                  v13);
    goto LABEL_26;
  }
  v15 = UuidFromStringW(a3, &Uuid);
  LastError = v15;
  if ( v15 >= 1 )
    LastError = (unsigned __int16)v15 | 0x80010000;
  if ( (LastError & 0x80000000) != 0 )
  {
    v16 = LastError;
    v17 = 39;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UserProcess\\core\\SessionHost.cpp",
      (const char *)v16,
      v20);
    goto LABEL_26;
  }
  v18 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v22);
  LastError = v18;
  if ( v18 < 0 )
  {
    v17 = 40;
LABEL_23:
    v16 = (unsigned int)v18;
    goto LABEL_24;
  }
  RegisterProxyStubCLSIDs(1);
  v21 = Uuid;
  v20 = v11;
  v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, UUID *, unsigned __int64))(*(_QWORD *)v22 + 24LL))(
          v22,
          a1,
          &v21,
          v10);
  LastError = v18;
  if ( v18 < 0 )
  {
    v17 = 48;
    goto LABEL_23;
  }
  LastError = 0;
LABEL_26:
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return LastError;
}

```

## disassembly

```asm
0x1400066b0  push    rbp
0x1400066b2  push    rbx
0x1400066b3  push    rsi
0x1400066b4  push    rdi
0x1400066b5  push    r12
0x1400066b7  push    r13
0x1400066b9  push    r14
0x1400066bb  push    r15
0x1400066bd  lea     rbp, [rsp-0Fh]
0x1400066c2  sub     rsp, 88h
0x1400066c9  mov     rax, cs:__security_cookie
0x1400066d0  xor     rax, rsp
0x1400066d3  mov     [rbp+47h+var_50], rax
0x1400066d7  mov     rbx, r8
0x1400066da  mov     r15, rdx
0x1400066dd  mov     r14, rcx
0x1400066e0  mov     rdi, [rbp+47h+String]
0x1400066e4  mov     rsi, [rbp+47h+arg_28]
0x1400066e8  xor     eax, eax
0x1400066ea  test    rcx, rcx
0x1400066ed  jz      loc_1400068B8
0x1400066f3  cmp     [rcx], ax
0x1400066f6  jz      loc_1400068B8
0x1400066fc  test    rdx, rdx
0x1400066ff  jnz     short loc_140006709
0x140006701  lea     edx, [rax+16h]
0x140006704  jmp     loc_1400068BD
0x140006709  test    rbx, rbx
0x14000670c  jz      loc_1400068B1
0x140006712  cmp     [r8], ax
0x140006716  jz      loc_1400068B1
0x14000671c  test    r9, r9
0x14000671f  jz      loc_1400068AA
0x140006725  cmp     [r9], ax
0x140006729  jz      loc_1400068AA
0x14000672f  test    rdi, rdi
0x140006732  jz      loc_1400068A3
0x140006738  cmp     [rdi], ax
0x14000673b  jz      loc_1400068A3
0x140006741  test    rsi, rsi
0x140006744  jz      loc_14000689C
0x14000674a  cmp     [rsi], ax
0x14000674d  jz      loc_14000689C
0x140006753  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000675a  movdqu  xmmword ptr [rbp+47h+Uuid.Data1], xmm0
0x14000675f  mov     [rbp+47h+var_70], rax
0x140006763  mov     r13d, 0Ah
0x140006769  mov     r8d, r13d; Radix
0x14000676c  xor     edx, edx; EndPtr
0x14000676e  mov     rcx, r9; String
0x140006771  call    _o_wcstoull_0
0x140006776  mov     r12, rax
0x140006779  mov     r8d, r13d; Radix
0x14000677c  xor     edx, edx; EndPtr
0x14000677e  mov     rcx, rdi; String
0x140006781  call    _o_wcstoull_0
0x140006786  mov     r13, rax
0x140006789  xor     edx, edx; EndPtr
0x14000678b  lea     r8d, [rdx+0Ah]; Radix
0x14000678f  mov     rcx, rsi; String
0x140006792  call    _o_wcstoull_0
0x140006797  mov     rsi, rax
0x14000679a  mov     edx, 4; lpProcName
0x14000679f  mov     rcx, r15; hModule
0x1400067a2  call    cs:__imp_GetProcAddress
0x1400067a8  mov     rdi, rax
0x1400067ab  test    rax, rax
0x1400067ae  jnz     short loc_1400067CA
0x1400067b0  mov     rcx, [rbp+4Fh]; this
0x1400067b4  lea     r8, aCW1SSrcClientU; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x1400067bb  lea     edx, [rax+25h]; void *
0x1400067be  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400067c3  mov     ebx, eax
0x1400067c5  jmp     loc_140006884
0x1400067ca  lea     rdx, [rbp+47h+Uuid]; Uuid
0x1400067ce  mov     rcx, rbx; StringUuid
0x1400067d1  call    cs:__imp_UuidFromStringW
0x1400067d7  mov     ebx, eax
0x1400067d9  cmp     eax, 1
0x1400067dc  jl      short loc_1400067E7
0x1400067de  movzx   ebx, ax
0x1400067e1  or      ebx, 80010000h
0x1400067e7  test    ebx, ebx
0x1400067e9  jns     short loc_1400067F5
0x1400067eb  mov     r9d, ebx
0x1400067ee  mov     edx, 27h ; '''
0x1400067f3  jmp     short loc_140006870
0x1400067f5  mov     rcx, [rbp+47h+var_70]
0x1400067f9  test    rcx, rcx
0x1400067fc  jz      short loc_140006812
0x1400067fe  mov     rax, [rcx]
0x140006801  mov     rax, [rax+10h]
0x140006805  call    _guard_dispatch_icall
0x14000680a  mov     [rbp+47h+var_70], 0
0x140006812  lea     rcx, [rbp+47h+var_70]
0x140006816  mov     rax, rdi
0x140006819  call    _guard_dispatch_icall
0x14000681e  mov     ebx, eax
0x140006820  test    eax, eax
0x140006822  jns     short loc_14000682B
0x140006824  mov     edx, 28h ; '('
0x140006829  jmp     short loc_14000686D
0x14000682b  mov     ecx, 1; unsigned int
0x140006830  call    ?RegisterProxyStubCLSIDs@@YAXK@Z; RegisterProxyStubCLSIDs(ulong)
0x140006835  movaps  xmm0, xmmword ptr [rbp+47h+Uuid.Data1]
0x140006839  movdqa  [rbp+47h+var_80], xmm0
0x14000683e  mov     rcx, [rbp+47h+var_70]
0x140006842  mov     rax, [rcx]
0x140006845  mov     [rsp+0C0h+var_98], rsi
0x14000684a  mov     qword ptr [rsp+0C0h+var_A0], r13; int
0x14000684f  mov     r9, r12
0x140006852  lea     r8, [rbp+47h+var_80]
0x140006856  mov     rdx, r14
0x140006859  mov     rax, [rax+18h]
0x14000685d  call    _guard_dispatch_icall
0x140006862  mov     ebx, eax
0x140006864  test    eax, eax
0x140006866  jns     short loc_140006882
0x140006868  mov     edx, 30h ; '0'; void *
0x14000686d  mov     r9d, eax; char *
0x140006870  mov     rcx, [rbp+4Fh]; this
0x140006874  lea     r8, aCW1SSrcClientU; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x14000687b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006880  jmp     short loc_140006884
0x140006882  xor     ebx, ebx
0x140006884  mov     rcx, [rbp+47h+var_70]
0x140006888  test    rcx, rcx
0x14000688b  jz      short loc_14000689A
0x14000688d  mov     rdx, [rcx]
0x140006890  mov     rax, [rdx+10h]
0x140006894  call    _guard_dispatch_icall
0x140006899  nop
0x14000689a  jmp     short loc_1400068D5
0x14000689c  mov     edx, 1Ah
0x1400068a1  jmp     short loc_1400068BD
0x1400068a3  mov     edx, 19h
0x1400068a8  jmp     short loc_1400068BD
0x1400068aa  mov     edx, 18h
0x1400068af  jmp     short loc_1400068BD
0x1400068b1  mov     edx, 17h
0x1400068b6  jmp     short loc_1400068BD
0x1400068b8  mov     edx, 15h; void *
0x1400068bd  mov     ebx, 80070057h
0x1400068c2  mov     r9d, ebx; char *
0x1400068c5  lea     r8, aCW1SSrcClientU; "C:\\__w\\1\\s\\src\\Client\\UserProcess"...
0x1400068cc  mov     rcx, [rbp+4Fh]; this
0x1400068d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400068d5  mov     eax, ebx
0x1400068d7  mov     rcx, [rbp+47h+var_50]
0x1400068db  xor     rcx, rsp; StackCookie
0x1400068de  call    __security_check_cookie
0x1400068e3  add     rsp, 88h
0x1400068ea  pop     r15
0x1400068ec  pop     r14
0x1400068ee  pop     r13
0x1400068f0  pop     r12
0x1400068f2  pop     rdi
0x1400068f3  pop     rsi
0x1400068f4  pop     rbx
0x1400068f5  pop     rbp
0x1400068f6  retn
```
