# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000b2d0`
- end: `0x18000b558`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `648`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bcbc`

## callees

- `0x180009728`
- `0x18000b2d0`
- `0x180021740`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000b404`
- `msvcrt!wcsncpy_s` at `0x18000b404`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b449`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b449`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b412`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b412`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b50e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b50e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b394`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b3c5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b49e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b4c8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b394`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b3c5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b49e`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b4c8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000b431`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000b431`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b361`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b361`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b34f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b34f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4f5`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rdi
  __int64 v17; // rax
  LPCWSTR v18; // rbp
  int v19; // ebx
  const unsigned __int16 *v20; // rbx
  __int64 v21; // r8
  const WCHAR *i; // rax
  unsigned int v23; // ebx
  _DWORD v24[2]; // [rsp+20h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-80h]
  wchar_t Destination[32]; // [rsp+30h] [rbp-78h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v24[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v24[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_44:
    v23 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_45;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_41:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v15, 1) )
      goto LABEL_49;
LABEL_42:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_44;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_41;
  }
  if ( !v13 )
    goto LABEL_48;
  v16 = 0;
  while ( v14 )
  {
    if ( v14 == 37 )
    {
      v16 = v13;
      break;
    }
    v13 = CharNextW(v13);
    v14 = *v13;
  }
  if ( !v16 )
    goto LABEL_48;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v23 = -2147467259;
    goto LABEL_45;
  }
  wcsncpy_s(Destination, 0x20u, *this, (int)v17);
  v18 = this[1];
  EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
  v19 = 0;
  if ( *((int *)v18 + 6) <= 0 )
    goto LABEL_27;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v18 + 1) + 8LL * v19), Destination) )
  {
    if ( ++v19 >= *((_DWORD *)v18 + 6) )
      goto LABEL_27;
  }
  if ( v19 == -1 )
  {
LABEL_27:
    v20 = 0;
  }
  else
  {
    if ( v19 < 0 || v19 >= *((_DWORD *)v18 + 6) )
    {
      RaiseException(0xC000008C, 1u, 0, 0);
      __debugbreak();
    }
    v20 = *(const unsigned __int16 **)(*((_QWORD *)v18 + 2) + 8LL * v19);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 16));
  if ( !v20 )
  {
LABEL_48:
    v23 = -2147352567;
    goto LABEL_45;
  }
  v21 = -1;
  do
    ++v21;
  while ( v20[v21] );
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v24, v20, v21) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_42;
  }
LABEL_49:
  v23 = -2147024882;
LABEL_45:
  CoTaskMemFree(pv);
  return v23;
}

```

## disassembly

```asm
0x18000b2d0  mov     [rsp+arg_8], rbx
0x18000b2d5  mov     [rsp+arg_18], rbp
0x18000b2da  push    rsi
0x18000b2db  push    rdi
0x18000b2dc  push    r12
0x18000b2de  push    r14
0x18000b2e0  push    r15
0x18000b2e2  sub     rsp, 80h
0x18000b2e9  mov     rax, cs:__security_cookie
0x18000b2f0  xor     rax, rsp
0x18000b2f3  mov     [rsp+0A8h+var_38], rax
0x18000b2f8  xor     r12d, r12d
0x18000b2fb  mov     r14, r8
0x18000b2fe  mov     rbx, rdx
0x18000b301  mov     rsi, rcx
0x18000b304  test    rdx, rdx
0x18000b307  jz      loc_18000B52A
0x18000b30d  test    r8, r8
0x18000b310  jz      loc_18000B52A
0x18000b316  mov     [r8], r12
0x18000b319  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b31d  inc     rax
0x18000b320  cmp     [rdx+rax*2], r12w
0x18000b325  jnz     short loc_18000B31D
0x18000b327  add     eax, eax
0x18000b329  mov     [rsp+0A8h+var_88], r12d
0x18000b32e  cmp     eax, 64h ; 'd'
0x18000b331  mov     ecx, 3E8h
0x18000b336  cmovl   eax, ecx
0x18000b339  mov     ecx, eax
0x18000b33b  mov     [rsp+0A8h+var_84], eax
0x18000b33f  add     rcx, rcx
0x18000b342  mov     eax, 0FFFFFFFFh
0x18000b347  cmp     rcx, rax
0x18000b34a  jbe     short loc_18000B35F
0x18000b34c  mov     rcx, r12; pv
0x18000b34f  call    cs:__imp_CoTaskMemFree
0x18000b355  mov     eax, 8007000Eh
0x18000b35a  jmp     loc_18000B52F
0x18000b35f  mov     ecx, ecx; cb
0x18000b361  call    cs:__imp_CoTaskMemAlloc
0x18000b367  mov     [rsp+0A8h+pv], rax
0x18000b36c  mov     rcx, rax
0x18000b36f  test    rax, rax
0x18000b372  jz      short loc_18000B34F
0x18000b374  mov     [rax], r12w
0x18000b378  mov     [rsi], rbx
0x18000b37b  movzx   eax, word ptr [rbx]
0x18000b37e  test    ax, ax
0x18000b381  jz      loc_18000B4E5
0x18000b387  cmp     ax, 25h ; '%'
0x18000b38b  jnz     loc_18000B4AE
0x18000b391  mov     rcx, rbx; lpsz
0x18000b394  call    cs:__imp_CharNextW
0x18000b39a  mov     [rsi], rax
0x18000b39d  movzx   ecx, word ptr [rax]
0x18000b3a0  cmp     cx, 25h ; '%'
0x18000b3a4  jnz     short loc_18000B3AE
0x18000b3a6  mov     rdx, rax
0x18000b3a9  jmp     loc_18000B4B1
0x18000b3ae  test    rax, rax
0x18000b3b1  jz      loc_18000B51C
0x18000b3b7  mov     rdi, r12
0x18000b3ba  jmp     short loc_18000B3CE
0x18000b3bc  cmp     cx, 25h ; '%'
0x18000b3c0  jz      short loc_18000B3D5
0x18000b3c2  mov     rcx, rax; lpsz
0x18000b3c5  call    cs:__imp_CharNextW
0x18000b3cb  movzx   ecx, word ptr [rax]
0x18000b3ce  test    cx, cx
0x18000b3d1  jnz     short loc_18000B3BC
0x18000b3d3  jmp     short loc_18000B3D8
0x18000b3d5  mov     rdi, rax
0x18000b3d8  test    rdi, rdi
0x18000b3db  jz      loc_18000B51C
0x18000b3e1  mov     rax, rdi
0x18000b3e4  sub     rax, [rsi]
0x18000b3e7  sar     rax, 1
0x18000b3ea  cmp     rax, 1Fh
0x18000b3ee  jg      loc_18000B515
0x18000b3f4  mov     r8, [rsi]; Source
0x18000b3f7  lea     rcx, [rsp+0A8h+Destination]; Destination
0x18000b3fc  movsxd  r9, eax; MaxCount
0x18000b3ff  mov     edx, 20h ; ' '; SizeInWords
0x18000b404  call    cs:__imp_wcsncpy_s
0x18000b40a  mov     rbp, [rsi+8]
0x18000b40e  lea     rcx, [rbp+20h]; lpCriticalSection
0x18000b412  call    cs:__imp_EnterCriticalSection
0x18000b418  mov     ebx, r12d
0x18000b41b  cmp     [rbp+18h], r12d
0x18000b41f  jle     short loc_18000B442
0x18000b421  mov     rcx, [rbp+8]
0x18000b425  lea     rdx, [rsp+0A8h+Destination]; lpString2
0x18000b42a  movsxd  rax, ebx
0x18000b42d  mov     rcx, [rcx+rax*8]; lpString1
0x18000b431  call    cs:__imp_lstrcmpiW
0x18000b437  test    eax, eax
0x18000b439  jz      short loc_18000B480
0x18000b43b  inc     ebx
0x18000b43d  cmp     ebx, [rbp+18h]
0x18000b440  jl      short loc_18000B421
0x18000b442  mov     rbx, r12
0x18000b445  lea     rcx, [rbp+20h]; lpCriticalSection
0x18000b449  call    cs:__imp_LeaveCriticalSection
0x18000b44f  test    rbx, rbx
0x18000b452  jz      loc_18000B51C
0x18000b458  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b45c  inc     r8; int
0x18000b45f  cmp     [rbx+r8*2], r12w
0x18000b464  jnz     short loc_18000B45C
0x18000b466  mov     rdx, rbx; unsigned __int16 *
0x18000b469  lea     rcx, [rsp+0A8h+var_88]; this
0x18000b46e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000b473  test    eax, eax
0x18000b475  jz      loc_18000B523
0x18000b47b  mov     rax, [rsi]
0x18000b47e  jmp     short loc_18000B4A7
0x18000b480  cmp     ebx, 0FFFFFFFFh
0x18000b483  jz      short loc_18000B442
0x18000b485  test    ebx, ebx
0x18000b487  js      short loc_18000B4FF
0x18000b489  cmp     ebx, [rbp+18h]
0x18000b48c  jge     short loc_18000B4FF
0x18000b48e  mov     rax, [rbp+10h]
0x18000b492  movsxd  rcx, ebx
0x18000b495  mov     rbx, [rax+rcx*8]
0x18000b499  jmp     short loc_18000B445
0x18000b49b  mov     rcx, rax; lpsz
0x18000b49e  call    cs:__imp_CharNextW
0x18000b4a4  mov     [rsi], rax
0x18000b4a7  cmp     rax, rdi
0x18000b4aa  jnz     short loc_18000B49B
0x18000b4ac  jmp     short loc_18000B4C5
0x18000b4ae  mov     rdx, rbx; unsigned __int16 *
0x18000b4b1  mov     r8d, 1; int
0x18000b4b7  lea     rcx, [rsp+0A8h+var_88]; this
0x18000b4bc  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000b4c1  test    eax, eax
0x18000b4c3  jz      short loc_18000B523
0x18000b4c5  mov     rcx, [rsi]; lpsz
0x18000b4c8  call    cs:__imp_CharNextW
0x18000b4ce  mov     rbx, rax
0x18000b4d1  mov     [rsi], rax
0x18000b4d4  movzx   eax, word ptr [rax]
0x18000b4d7  test    ax, ax
0x18000b4da  jnz     loc_18000B387
0x18000b4e0  mov     rcx, [rsp+0A8h+pv]
0x18000b4e5  mov     ebx, r12d
0x18000b4e8  mov     [rsp+0A8h+pv], r12
0x18000b4ed  mov     [r14], rcx
0x18000b4f0  mov     rcx, [rsp+0A8h+pv]; pv
0x18000b4f5  call    cs:__imp_CoTaskMemFree
0x18000b4fb  mov     eax, ebx
0x18000b4fd  jmp     short loc_18000B52F
0x18000b4ff  xor     r9d, r9d; lpArguments
0x18000b502  xor     r8d, r8d; nNumberOfArguments
0x18000b505  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000b50a  lea     edx, [r9+1]; dwExceptionFlags
0x18000b50e  call    cs:__imp_RaiseException
0x18000b514  int     3; Trap to Debugger
0x18000b515  mov     ebx, 80004005h
0x18000b51a  jmp     short loc_18000B4F0
0x18000b51c  mov     ebx, 80020009h
0x18000b521  jmp     short loc_18000B4F0
0x18000b523  mov     ebx, 8007000Eh
0x18000b528  jmp     short loc_18000B4F0
0x18000b52a  mov     eax, 80004003h
0x18000b52f  mov     rcx, [rsp+0A8h+var_38]
0x18000b534  xor     rcx, rsp; StackCookie
0x18000b537  call    __security_check_cookie
0x18000b53c  lea     r11, [rsp+0A8h+var_28]
0x18000b544  mov     rbx, [r11+38h]
0x18000b548  mov     rbp, [r11+48h]
0x18000b54c  mov     rsp, r11
0x18000b54f  pop     r15
0x18000b551  pop     r14
0x18000b553  pop     r12
0x18000b555  pop     rdi
0x18000b556  pop     rsi
0x18000b557  retn
```
