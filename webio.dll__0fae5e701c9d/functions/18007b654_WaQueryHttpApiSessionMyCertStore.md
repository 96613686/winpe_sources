# WaQueryHttpApiSessionMyCertStore

- ea: `0x18007b654`
- end: `0x18007b7e9`
- name: `WaQueryHttpApiSessionMyCertStore`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007b94c`

## callees

- `0x18007b654`
- `0x1800971ec`
- `0x180097810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b74c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b74c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007b693`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007b693`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007b6b0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007b6b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007b6c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007b6c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b77f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b7ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b77f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b7ad`
- `CRYPT32!CertControlStore` at `0x18007b73c`
- `CRYPT32!CertControlStore` at `0x18007b73c`
- `CRYPT32!CertOpenStore` at `0x18007b700`
- `CRYPT32!CertOpenStore` at `0x18007b700`
- `CRYPT32!CertCloseStore` at `0x18007b795`
- `CRYPT32!CertCloseStore` at `0x18007b795`

## pseudocode

```c
__int64 __fastcall WaQueryHttpApiSessionMyCertStore(RTL_SRWLOCK *a1, _QWORD *a2)
{
  DWORD v4; // edi
  char v5; // bl
  PVOID Ptr; // rax
  PVOID v7; // rax
  void *v8; // rbx
  HCERTSTORE v9; // rax
  DWORD LastError; // eax
  __int64 v11; // rdx

  v4 = 0;
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_q(1050, 15, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, a1);
  *a2 = 0;
  v5 = 0;
  AcquireSRWLockShared(a1 + 4);
  Ptr = a1[5].Ptr;
  if ( Ptr )
  {
    *a2 = Ptr;
    v5 = 1;
  }
  ReleaseSRWLockShared(a1 + 4);
  if ( !v5 )
  {
    AcquireSRWLockExclusive(a1 + 4);
    v7 = a1[5].Ptr;
    if ( v7 )
    {
      v8 = 0;
      *a2 = v7;
      goto LABEL_15;
    }
    v9 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x18000u, L"my");
    v8 = v9;
    if ( v9 )
    {
      if ( CertControlStore(v9, 0, 4u, 0) )
      {
        a1[5].Ptr = v8;
        *a2 = v8;
        ReleaseSRWLockExclusive(a1 + 4);
        goto LABEL_18;
      }
      LastError = GetLastError();
      v4 = LastError;
      if ( (BYTE3(xmmword_1800AD710) & 4) == 0 )
        goto LABEL_15;
      v11 = 17;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( (BYTE3(xmmword_1800AD710) & 4) == 0 )
        goto LABEL_15;
      v11 = 16;
    }
    WPP_SF_d(538, v11, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, LastError);
LABEL_15:
    ReleaseSRWLockExclusive(a1 + 4);
    if ( v8 )
      CertCloseStore(v8, 0);
  }
LABEL_18:
  if ( (BYTE3(xmmword_1800AD720) & 4) != 0 )
    WPP_SF_d(1050, 18, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18007b654  push    rbx
0x18007b656  push    rbp
0x18007b657  push    rsi
0x18007b658  push    rdi
0x18007b659  push    r14
0x18007b65b  sub     rsp, 30h
0x18007b65f  mov     r14, rdx
0x18007b662  mov     rsi, rcx
0x18007b665  xor     edi, edi
0x18007b667  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007b66e  jz      short loc_18007B687
0x18007b670  lea     edx, [rdi+0Fh]
0x18007b673  mov     ecx, 41Ah
0x18007b678  mov     r9, rsi
0x18007b67b  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007b682  call    WPP_SF_q
0x18007b687  lea     rbp, [rsi+20h]
0x18007b68b  mov     [r14], rdi
0x18007b68e  mov     rcx, rbp; SRWLock
0x18007b691  xor     bl, bl
0x18007b693  call    cs:__imp_AcquireSRWLockShared
0x18007b69a  nop     dword ptr [rax+rax+00h]
0x18007b69f  mov     rax, [rsi+28h]
0x18007b6a3  test    rax, rax
0x18007b6a6  jz      short loc_18007B6AD
0x18007b6a8  mov     [r14], rax
0x18007b6ab  mov     bl, 1
0x18007b6ad  mov     rcx, rbp; SRWLock
0x18007b6b0  call    cs:__imp_ReleaseSRWLockShared
0x18007b6b7  nop     dword ptr [rax+rax+00h]
0x18007b6bc  test    bl, bl
0x18007b6be  jnz     loc_18007B7B9
0x18007b6c4  mov     rcx, rbp; SRWLock
0x18007b6c7  call    cs:__imp_AcquireSRWLockExclusive
0x18007b6ce  nop     dword ptr [rax+rax+00h]
0x18007b6d3  mov     rax, [rsi+28h]
0x18007b6d7  test    rax, rax
0x18007b6da  jz      short loc_18007B6E6
0x18007b6dc  xor     ebx, ebx
0x18007b6de  mov     [r14], rax
0x18007b6e1  jmp     loc_18007B77C
0x18007b6e6  xor     edx, edx; dwEncodingType
0x18007b6e8  lea     rax, aMy; "my"
0x18007b6ef  mov     r9d, 18000h; dwFlags
0x18007b6f5  mov     [rsp+58h+pvPara], rax; pvPara
0x18007b6fa  xor     r8d, r8d; hCryptProv
0x18007b6fd  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18007b700  call    cs:__imp_CertOpenStore
0x18007b707  nop     dword ptr [rax+rax+00h]
0x18007b70c  mov     rbx, rax
0x18007b70f  test    rax, rax
0x18007b712  jnz     short loc_18007B730
0x18007b714  call    cs:__imp_GetLastError
0x18007b71b  nop     dword ptr [rax+rax+00h]
0x18007b720  mov     edi, eax
0x18007b722  test    byte ptr cs:xmmword_1800AD710+3, 4
0x18007b729  jz      short loc_18007B77C
0x18007b72b  lea     edx, [rbx+10h]
0x18007b72e  jmp     short loc_18007B768
0x18007b730  xor     r9d, r9d; pvCtrlPara
0x18007b733  xor     edx, edx; dwFlags
0x18007b735  mov     rcx, rbx; hCertStore
0x18007b738  lea     r8d, [r9+4]; dwCtrlType
0x18007b73c  call    cs:__imp_CertControlStore
0x18007b743  nop     dword ptr [rax+rax+00h]
0x18007b748  test    eax, eax
0x18007b74a  jnz     short loc_18007B7A3
0x18007b74c  call    cs:__imp_GetLastError
0x18007b753  nop     dword ptr [rax+rax+00h]
0x18007b758  mov     edi, eax
0x18007b75a  test    byte ptr cs:xmmword_1800AD710+3, 4
0x18007b761  jz      short loc_18007B77C
0x18007b763  mov     edx, 11h
0x18007b768  mov     r9d, eax
0x18007b76b  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007b772  mov     ecx, 21Ah
0x18007b777  call    WPP_SF_d
0x18007b77c  mov     rcx, rbp; SRWLock
0x18007b77f  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b786  nop     dword ptr [rax+rax+00h]
0x18007b78b  test    rbx, rbx
0x18007b78e  jz      short loc_18007B7B9
0x18007b790  xor     edx, edx; dwFlags
0x18007b792  mov     rcx, rbx; hCertStore
0x18007b795  call    cs:__imp_CertCloseStore
0x18007b79c  nop     dword ptr [rax+rax+00h]
0x18007b7a1  jmp     short loc_18007B7B9
0x18007b7a3  mov     rcx, rbp; SRWLock
0x18007b7a6  mov     [rsi+28h], rbx
0x18007b7aa  mov     [r14], rbx
0x18007b7ad  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b7b4  nop     dword ptr [rax+rax+00h]
0x18007b7b9  test    byte ptr cs:xmmword_1800AD720+3, 4
0x18007b7c0  jz      short loc_18007B7DB
0x18007b7c2  mov     edx, 12h
0x18007b7c7  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x18007b7ce  mov     ecx, 41Ah
0x18007b7d3  mov     r9d, edi
0x18007b7d6  call    WPP_SF_d
0x18007b7db  mov     eax, edi
0x18007b7dd  add     rsp, 30h
0x18007b7e1  pop     r14
0x18007b7e3  pop     rdi
0x18007b7e4  pop     rsi
0x18007b7e5  pop     rbp
0x18007b7e6  pop     rbx
0x18007b7e7  retn
```
