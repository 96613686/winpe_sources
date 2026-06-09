# CINetEdge::GetPreviouslySubmittedCredential(ushort * *)

- ea: `0x1800ec0d4`
- end: `0x1800ec315`
- name: `?GetPreviouslySubmittedCredential@CINetEdge@@IEAAHPEAPEAG@Z`
- size: `577`
- prototype: `__int64 __fastcall(CINetEdge *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800eab70`

## callees

- `0x18000b2e0`
- `0x18000b490`
- `0x1800ec0d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec204`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ec183`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ec222`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ec183`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ec222`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec2b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec2ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec2b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ec2ec`
- `WININET!InternetQueryOptionW` at `0x1800ec14b`
- `WININET!InternetQueryOptionW` at `0x1800ec1bd`
- `WININET!InternetQueryOptionW` at `0x1800ec1f6`
- `WININET!InternetQueryOptionW` at `0x1800ec258`
- `WININET!InternetQueryOptionW` at `0x1800ec14b`
- `WININET!InternetQueryOptionW` at `0x1800ec1bd`
- `WININET!InternetQueryOptionW` at `0x1800ec1f6`
- `WININET!InternetQueryOptionW` at `0x1800ec258`

## pseudocode

```c
__int64 __fastcall CINetEdge::GetPreviouslySubmittedCredential(CINetEdge *this, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  void *v5; // rcx
  bool v6; // cf
  unsigned __int16 *v7; // rsi
  _WORD *v8; // rdi
  BOOL v9; // ebx
  DWORD LastError; // eax
  __int64 v11; // r15
  unsigned __int16 *v12; // rax
  void *v13; // rcx
  DWORD v14; // eax
  _WORD *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int16 *i; // rax
  __int64 v19; // rcx
  _BYTE *j; // rax
  CINetEdge *v22; // [rsp+20h] [rbp-18h] BYREF
  char v23; // [rsp+28h] [rbp-10h]
  DWORD dwBufferLength; // [rsp+88h] [rbp+50h] BYREF

  v4 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v22 = this;
    v23 = 0;
    _InterlockedIncrement((volatile signed __int32 *)this + 300);
    if ( !CINetEdge::CAutoStateLock::AcquireLock((CINetEdge::CAutoStateLock *)&v22) )
    {
LABEL_28:
      CINetEdge::CAutoStateLock::~CAutoStateLock((CINetEdge::CAutoStateLock *)&v22);
      return v4;
    }
    v5 = (void *)*((_QWORD *)this + 47);
    v6 = (*((_BYTE *)this + 976) & 1) != 0;
    dwBufferLength = 0;
    v7 = 0;
    v8 = 0;
    v9 = InternetQueryOptionW(v5, v6 ? 43 : 28, 0, &dwBufferLength);
    LastError = GetLastError();
    v11 = -1;
    if ( v9
      || LastError == 122
      && dwBufferLength
      && (v12 = (unsigned __int16 *)CoTaskMemAlloc(dwBufferLength), (v7 = v12) != 0)
      && InternetQueryOptionW(
           *((HINTERNET *)this + 47),
           (*((_BYTE *)this + 976) & 1) != 0 ? 43 : 28,
           v12,
           &dwBufferLength) )
    {
      v13 = (void *)*((_QWORD *)this + 47);
      v6 = (*((_BYTE *)this + 976) & 1) != 0;
      dwBufferLength = 0;
      v4 = InternetQueryOptionW(v13, v6 ? 44 : 29, 0, &dwBufferLength);
      v14 = GetLastError();
      if ( v4
        || v14 == 122
        && dwBufferLength
        && (v15 = CoTaskMemAlloc(dwBufferLength), (v8 = v15) != 0)
        && (v4 = InternetQueryOptionW(
                   *((HINTERNET *)this + 47),
                   (*((_BYTE *)this + 976) & 1) != 0 ? 44 : 29,
                   v15,
                   &dwBufferLength)) != 0 )
      {
        if ( !v7 )
          goto LABEL_23;
        if ( *v7 && v8 && *v8 )
        {
          *a2 = v7;
          goto LABEL_24;
        }
      }
    }
    if ( v7 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v7[v16] );
      v17 = 2 * v16;
      for ( i = v7; v17; --v17 )
      {
        *(_BYTE *)i = 0;
        i = (unsigned __int16 *)((char *)i + 1);
      }
    }
LABEL_23:
    CoTaskMemFree(v7);
    v4 = 0;
    if ( !v8 )
    {
LABEL_27:
      CoTaskMemFree(v8);
      goto LABEL_28;
    }
    do
LABEL_24:
      ++v11;
    while ( v8[v11] );
    v19 = 2 * v11;
    for ( j = v8; v19; --v19 )
      *j++ = 0;
    goto LABEL_27;
  }
  return v4;
}

```

## disassembly

```asm
0x1800ec0d4  push    rbp
0x1800ec0d6  push    rbx
0x1800ec0d7  push    rsi
0x1800ec0d8  push    rdi
0x1800ec0d9  push    r12
0x1800ec0db  push    r13
0x1800ec0dd  push    r14
0x1800ec0df  push    r15
0x1800ec0e1  mov     rbp, rsp
0x1800ec0e4  sub     rsp, 38h
0x1800ec0e8  xor     r13d, r13d
0x1800ec0eb  mov     r12, rdx
0x1800ec0ee  mov     r14, rcx
0x1800ec0f1  mov     ebx, r13d
0x1800ec0f4  test    rdx, rdx
0x1800ec0f7  jz      loc_1800EC301
0x1800ec0fd  mov     [rdx], r13
0x1800ec100  mov     [rbp+var_18], rcx
0x1800ec104  mov     [rbp+var_10], r13b
0x1800ec108  lock inc dword ptr [rcx+4B0h]
0x1800ec10f  lea     rcx, [rbp+var_18]; this
0x1800ec113  call    ?AcquireLock@CAutoStateLock@CINetEdge@@QEAA_NXZ; CINetEdge::CAutoStateLock::AcquireLock(void)
0x1800ec118  test    al, al
0x1800ec11a  jz      loc_1800EC2F8
0x1800ec120  mov     al, [r14+3D0h]
0x1800ec127  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x1800ec12b  mov     rcx, [r14+178h]; hInternet
0x1800ec132  and     al, 1
0x1800ec134  neg     al
0x1800ec136  mov     [rbp+dwBufferLength], r13d
0x1800ec13a  mov     esi, r13d
0x1800ec13d  mov     edi, r13d
0x1800ec140  sbb     edx, edx
0x1800ec142  xor     r8d, r8d; lpBuffer
0x1800ec145  and     edx, 0Fh
0x1800ec148  add     edx, 1Ch; dwOption
0x1800ec14b  call    cs:__imp_InternetQueryOptionW
0x1800ec152  nop     dword ptr [rax+rax+00h]
0x1800ec157  mov     ebx, eax
0x1800ec159  call    cs:__imp_GetLastError
0x1800ec160  nop     dword ptr [rax+rax+00h]
0x1800ec165  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800ec169  test    ebx, ebx
0x1800ec16b  jnz     short loc_1800EC1D1
0x1800ec16d  cmp     eax, 7Ah ; 'z'
0x1800ec170  jnz     loc_1800EC286
0x1800ec176  mov     eax, [rbp+dwBufferLength]
0x1800ec179  test    eax, eax
0x1800ec17b  jz      loc_1800EC286
0x1800ec181  mov     ecx, eax; cb
0x1800ec183  call    cs:__imp_CoTaskMemAlloc
0x1800ec18a  nop     dword ptr [rax+rax+00h]
0x1800ec18f  mov     rsi, rax
0x1800ec192  test    rax, rax
0x1800ec195  jz      loc_1800EC286
0x1800ec19b  mov     cl, [r14+3D0h]
0x1800ec1a2  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x1800ec1a6  and     cl, 1
0x1800ec1a9  mov     r8, rax; lpBuffer
0x1800ec1ac  neg     cl
0x1800ec1ae  mov     rcx, [r14+178h]; hInternet
0x1800ec1b5  sbb     edx, edx
0x1800ec1b7  and     edx, 0Fh
0x1800ec1ba  add     edx, 1Ch; dwOption
0x1800ec1bd  call    cs:__imp_InternetQueryOptionW
0x1800ec1c4  nop     dword ptr [rax+rax+00h]
0x1800ec1c9  test    eax, eax
0x1800ec1cb  jz      loc_1800EC286
0x1800ec1d1  mov     al, [r14+3D0h]
0x1800ec1d8  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x1800ec1dc  mov     rcx, [r14+178h]; hInternet
0x1800ec1e3  and     al, 1
0x1800ec1e5  neg     al
0x1800ec1e7  mov     [rbp+dwBufferLength], r13d
0x1800ec1eb  sbb     edx, edx
0x1800ec1ed  xor     r8d, r8d; lpBuffer
0x1800ec1f0  and     edx, 0Fh
0x1800ec1f3  add     edx, 1Dh; dwOption
0x1800ec1f6  call    cs:__imp_InternetQueryOptionW
0x1800ec1fd  nop     dword ptr [rax+rax+00h]
0x1800ec202  mov     ebx, eax
0x1800ec204  call    cs:__imp_GetLastError
0x1800ec20b  nop     dword ptr [rax+rax+00h]
0x1800ec210  test    ebx, ebx
0x1800ec212  jnz     short loc_1800EC26A
0x1800ec214  cmp     eax, 7Ah ; 'z'
0x1800ec217  jnz     short loc_1800EC286
0x1800ec219  mov     eax, [rbp+dwBufferLength]
0x1800ec21c  test    eax, eax
0x1800ec21e  jz      short loc_1800EC286
0x1800ec220  mov     ecx, eax; cb
0x1800ec222  call    cs:__imp_CoTaskMemAlloc
0x1800ec229  nop     dword ptr [rax+rax+00h]
0x1800ec22e  mov     rdi, rax
0x1800ec231  test    rax, rax
0x1800ec234  jz      short loc_1800EC286
0x1800ec236  mov     cl, [r14+3D0h]
0x1800ec23d  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x1800ec241  and     cl, 1
0x1800ec244  mov     r8, rax; lpBuffer
0x1800ec247  neg     cl
0x1800ec249  mov     rcx, [r14+178h]; hInternet
0x1800ec250  sbb     edx, edx
0x1800ec252  and     edx, 0Fh
0x1800ec255  add     edx, 1Dh; dwOption
0x1800ec258  call    cs:__imp_InternetQueryOptionW
0x1800ec25f  nop     dword ptr [rax+rax+00h]
0x1800ec264  mov     ebx, eax
0x1800ec266  test    eax, eax
0x1800ec268  jz      short loc_1800EC286
0x1800ec26a  test    rsi, rsi
0x1800ec26d  jz      short loc_1800EC2B0
0x1800ec26f  cmp     [rsi], r13w
0x1800ec273  jz      short loc_1800EC286
0x1800ec275  test    rdi, rdi
0x1800ec278  jz      short loc_1800EC286
0x1800ec27a  cmp     [rdi], r13w
0x1800ec27e  jz      short loc_1800EC286
0x1800ec280  mov     [r12], rsi
0x1800ec284  jmp     short loc_1800EC2C7
0x1800ec286  test    rsi, rsi
0x1800ec289  jz      short loc_1800EC2B0
0x1800ec28b  mov     rax, r15
0x1800ec28e  inc     rax
0x1800ec291  cmp     [rsi+rax*2], r13w
0x1800ec296  jnz     short loc_1800EC28E
0x1800ec298  lea     rcx, [rax+rax]
0x1800ec29c  mov     rax, rsi
0x1800ec29f  test    rcx, rcx
0x1800ec2a2  jz      short loc_1800EC2B0
0x1800ec2a4  mov     [rax], r13b
0x1800ec2a7  inc     rax
0x1800ec2aa  sub     rcx, 1
0x1800ec2ae  jnz     short loc_1800EC2A4
0x1800ec2b0  mov     rcx, rsi; pv
0x1800ec2b3  call    cs:__imp_CoTaskMemFree
0x1800ec2ba  nop     dword ptr [rax+rax+00h]
0x1800ec2bf  mov     ebx, r13d
0x1800ec2c2  test    rdi, rdi
0x1800ec2c5  jz      short loc_1800EC2E9
0x1800ec2c7  inc     r15
0x1800ec2ca  cmp     [rdi+r15*2], r13w
0x1800ec2cf  jnz     short loc_1800EC2C7
0x1800ec2d1  lea     rcx, [r15+r15]
0x1800ec2d5  mov     rax, rdi
0x1800ec2d8  test    rcx, rcx
0x1800ec2db  jz      short loc_1800EC2E9
0x1800ec2dd  mov     [rax], r13b
0x1800ec2e0  inc     rax
0x1800ec2e3  sub     rcx, 1
0x1800ec2e7  jnz     short loc_1800EC2DD
0x1800ec2e9  mov     rcx, rdi; pv
0x1800ec2ec  call    cs:__imp_CoTaskMemFree
0x1800ec2f3  nop     dword ptr [rax+rax+00h]
0x1800ec2f8  lea     rcx, [rbp+var_18]; this
0x1800ec2fc  call    ??1CAutoStateLock@CINetEdge@@QEAA@XZ; CINetEdge::CAutoStateLock::~CAutoStateLock(void)
0x1800ec301  mov     eax, ebx
0x1800ec303  add     rsp, 38h
0x1800ec307  pop     r15
0x1800ec309  pop     r14
0x1800ec30b  pop     r13
0x1800ec30d  pop     r12
0x1800ec30f  pop     rdi
0x1800ec310  pop     rsi
0x1800ec311  pop     rbx
0x1800ec312  pop     rbp
0x1800ec313  retn
```
