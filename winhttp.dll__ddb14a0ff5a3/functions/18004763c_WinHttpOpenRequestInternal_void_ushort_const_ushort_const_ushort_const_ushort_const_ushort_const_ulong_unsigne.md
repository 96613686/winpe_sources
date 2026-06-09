# WinHttpOpenRequestInternal(void *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const * *,ulong,unsigned __int64)

- ea: `0x18004763c`
- end: `0x180047c69`
- name: `?WinHttpOpenRequestInternal@@YAPEAXPEAXPEBG111PEAPEBGK_K@Z`
- size: `1581`
- prototype: `void *__usercall@<rax>(void *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 **, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180047480`

## callees

- `0x1800065a0`
- `0x180011f84`
- `0x180013e44`
- `0x1800241a0`
- `0x18002acec`
- `0x180033ac0`
- `0x18003b0e0`
- `0x18003ba00`
- `0x18003bc60`
- `0x180041eb0`
- `0x180043840`
- `0x180045580`
- `0x18004763c`
- `0x180047c70`
- `0x180047e14`
- `0x180047ea0`
- `0x180048c1c`
- `0x180048cc0`
- `0x180078f58`
- `0x18007fb68`
- `0x18009a8d8`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800cf008`
- `0x1800d4068`
- `0x1800db6b0`
- `0x1800db704`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800478bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800478bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800478dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800479ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800478dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800479ae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800479ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800479ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180047a47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180047a47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047a4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047a4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047a91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047a91`

## pseudocode

```c
__int64 __fastcall WinHttpOpenRequestInternal(
        void *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        __int64 a5,
        const unsigned __int16 **a6,
        unsigned int a7)
{
  const unsigned __int16 *v8; // rdi
  HTTP_REQUEST_HANDLE_OBJECT *v12; // rsi
  DWORD IsValid; // ebx
  struct HANDLE_OBJECT *v14; // rbx
  unsigned __int16 v15; // r14
  unsigned int v16; // r15d
  const unsigned __int16 **v17; // r13
  unsigned int v18; // eax
  HTTP_REQUEST_HANDLE_OBJECT *v19; // rcx
  __int64 v20; // rdx
  const unsigned __int16 *v21; // rax
  __int64 v22; // r14
  unsigned int v23; // r15d
  unsigned int v24; // edx
  unsigned __int64 v25; // r9
  HTTP_USER_REQUEST *v26; // rax
  HTTP_USER_REQUEST *v27; // rdi
  unsigned int v28; // ebx
  struct INTERNET_SESSION_HANDLE_OBJECT *RootHandle; // rax
  HTTP_USER_REQUEST *v30; // rax
  __int64 v31; // r14
  signed __int32 v32; // edi
  DWORD CurrentProcessId; // ebx
  DWORD CurrentThreadId; // eax
  unsigned int v36; // eax
  unsigned int v37; // edx
  unsigned int appended; // eax
  char v39[8]; // [rsp+20h] [rbp-91h]
  int v40; // [rsp+28h] [rbp-89h]
  int v41; // [rsp+60h] [rbp-51h]
  unsigned int v42; // [rsp+64h] [rbp-4Dh] BYREF
  const unsigned __int16 **v43; // [rsp+68h] [rbp-49h]
  __int64 v44; // [rsp+70h] [rbp-41h] BYREF
  HTTP_REQUEST_HANDLE_OBJECT *v45; // [rsp+78h] [rbp-39h] BYREF
  struct HANDLE_OBJECT *v46; // [rsp+80h] [rbp-31h]
  struct HANDLE_OBJECT *v47; // [rsp+88h] [rbp-29h] BYREF
  unsigned __int16 *v48; // [rsp+90h] [rbp-21h] BYREF
  unsigned int v49; // [rsp+98h] [rbp-19h] BYREF

  v8 = (const unsigned __int16 *)a5;
  v43 = a6;
  v48 = a2;
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_qSSSSqDP(
      (_DWORD)a1,
      (_DWORD)a2,
      (_DWORD)a3,
      (_DWORD)a1,
      (__int64)a2,
      (__int64)a3,
      (__int64)a4,
      a5,
      (__int64)a6,
      a7);
  v47 = 0;
  v12 = 0;
  v45 = 0;
  v44 = 0;
  v42 = 0;
  v49 = 0;
  if ( !a2 || (v41 = 1, !*a2) )
  {
    v41 = 0;
    v48 = L"GET";
  }
  if ( !GlobalDataInitialized )
  {
    IsValid = 12172;
    goto LABEL_39;
  }
  IsValid = MapHandleToAddress(a1, (void **)&v47, 0);
  if ( IsValid )
    goto LABEL_39;
  IsValid = HANDLE_OBJECT::IsValid(v47, 1852785480);
  if ( IsValid )
    goto LABEL_37;
  if ( (a7 & 0xFF7FFC33) != 0 )
  {
LABEL_71:
    IsValid = 87;
    goto LABEL_39;
  }
  IsValid = ParseVerb(&v48, &v42);
  if ( IsValid || (IsValid = ParseHttpVersion(a4, &v44)) != 0 )
  {
LABEL_39:
    if ( (xmmword_180107A50 & 2) != 0 )
      WPP_SF_d(513, 12, WPP_5ae54466eb4b39fe6c428c9cb8d9284a_Traceguids, IsValid, *(_QWORD *)v39);
    goto LABEL_58;
  }
  if ( a5 )
    v8 = (const unsigned __int16 *)(-(__int64)(*(_WORD *)a5 != 0) & a5);
  v14 = v47;
  v46 = v47;
  v15 = *((_WORD *)v47 + 206);
  if ( (unsigned int)IsInappropriateHTTPPort(v15) )
  {
    IsValid = 12005;
    goto LABEL_39;
  }
  v16 = a7 & 0x800000;
  if ( *((_DWORD *)GetRootHandle(v14) + 151) && !v16 )
  {
    IsValid = 5;
    goto LABEL_39;
  }
  if ( *((_DWORD *)v14 + 105) )
  {
    if ( !v41 && !a3 && !a4 && !v8 )
    {
      v17 = v43;
      if ( !v43 && !a7 )
        goto LABEL_17;
    }
    goto LABEL_71;
  }
  v17 = v43;
LABEL_17:
  v18 = RMakeHttpReqObjectHandle(v47, (void **)&v45, a7 & 0xFFDFFFFF);
  v12 = v45;
  IsValid = v18;
  if ( v18 )
    goto LABEL_37;
  if ( !v15 )
    v15 = v16 != 0 ? 443 : 80;
  *((_WORD *)v45 + 206) = v15;
  IsValid = CAnsiString::SetStringW((HTTP_REQUEST_HANDLE_OBJECT *)((char *)v12 + 776), v48, v42, 0, 0);
  if ( IsValid )
    goto LABEL_37;
  v19 = v12;
  if ( v16 )
    v19 = v12;
  *((_DWORD *)v19 + 104) = (v16 != 0) + 1;
  if ( a3 && *a3 )
  {
    HIDWORD(v43) = 0;
    v20 = 0x7FFFFFFF;
    v49 = 0;
    v21 = a3;
    do
    {
      if ( !*v21 )
        break;
      ++v21;
      --v20;
    }
    while ( v20 );
    v22 = (0x7FFFFFFF - v20) & -(__int64)(v20 != 0);
    if ( v20 )
    {
      v49 = v20 != 0 ? 0x7FFFFFFF - v20 : 0;
    }
    else
    {
      LODWORD(v22) = v49;
      HIDWORD(v43) = 81;
    }
    IsValid = WX_WIN32_FROM_HR(v20 == 0 ? 0x80070057 : 0);
    if ( !IsValid )
    {
      v23 = a7;
      IsValid = HTTP_REQUEST_HANDLE_OBJECT::SetPath(v12, a3, v22, a7);
      if ( !IsValid )
        goto LABEL_32;
    }
LABEL_37:
    if ( v12 )
    {
      HANDLE_OBJECT::Dereference(v12);
      WinHttpCloseHandle(*((HINTERNET *)v12 + 4));
    }
    goto LABEL_39;
  }
  IsValid = HTTP_REQUEST_HANDLE_OBJECT::SetPath(v12, L"/", 1u, 0x40u);
  if ( IsValid )
    goto LABEL_37;
  v23 = a7;
LABEL_32:
  *((_QWORD *)v12 + 96) = v44;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v12 + 712));
  if ( !v8 )
    goto LABEL_33;
  v25 = -1;
  do
    ++v25;
  while ( v8[v25] );
  if ( v25 > 0xFFFF )
  {
    IsValid = 87;
    goto LABEL_37;
  }
  IsValid = HTTP_REQUEST_HANDLE_OBJECT::SetRequestHeader(v12, v24, v8, v25, *(int *)v39);
  if ( IsValid )
  {
LABEL_47:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v12 + 712));
    goto LABEL_37;
  }
LABEL_33:
  if ( v17 )
  {
    while ( *v17 )
    {
      v36 = WxStringCchLengthDWordW(*v17, 0x7FFFFFFF, &v49);
      IsValid = WX_WIN32_FROM_HR(v36);
      if ( IsValid )
        goto LABEL_37;
      appended = HTTP_REQUEST_HANDLE_OBJECT::AppendRequestHeader(v12, v37, *v17, v49, v39[0], v40);
      IsValid = appended;
      if ( appended == 122 )
      {
        if ( (xmmword_180107A50 & 2) != 0 )
          WPP_SF_(513, 11, WPP_5ae54466eb4b39fe6c428c9cb8d9284a_Traceguids);
        IsValid = 87;
        goto LABEL_47;
      }
      if ( appended )
        goto LABEL_47;
      ++v17;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v12 + 712));
  HTTP_REQUEST_HANDLE_OBJECT::SetState(v12);
  *((_DWORD *)v12 + 206) = 0;
  if ( (v23 & 0x200000) != 0 )
    HTTP_REQUEST_HANDLE_OBJECT::SetDwordOption(v12, 0x58u, 0);
  IsValid = HTTP_REQUEST_HANDLE_OBJECT::UpdateURL(v12);
  if ( IsValid )
    goto LABEL_37;
  v26 = (HTTP_USER_REQUEST *)HeapAlloc(g_hWxProcessHeap, 0, 0x29D0u);
  v27 = v26;
  if ( !v26
    || (memset_0(v26, 0, 0x29D0u),
        v28 = *((_DWORD *)GetRootHandle(v46) + 114),
        RootHandle = GetRootHandle(v46),
        (v30 = HTTP_USER_REQUEST::HTTP_USER_REQUEST(v27, v12, *((_DWORD *)RootHandle + 113), v28)) == 0) )
  {
    IsValid = 8;
    goto LABEL_37;
  }
  *((_QWORD *)v12 + 56) = v30;
  if ( !(unsigned int)HANDLE_OBJECT::Dereference(v12) )
  {
    v31 = *((_QWORD *)v12 + 4);
    v32 = _InterlockedIncrement((volatile signed __int32 *)&g_dwActivityIdCount);
    CurrentProcessId = GetCurrentProcessId();
    CurrentThreadId = GetCurrentThreadId();
    *((_DWORD *)v12 + 46) = v31;
    *((_DWORD *)v12 + 48) = CurrentProcessId ^ (CurrentThreadId << 16);
    IsValid = 0;
    *((_DWORD *)v12 + 47) = v32;
    *((_DWORD *)v12 + 49) = (_DWORD)v12;
    goto LABEL_52;
  }
  IsValid = 12017;
LABEL_58:
  v31 = 0;
LABEL_52:
  if ( v47 )
  {
    DereferenceObject(v47);
    v47 = 0;
  }
  if ( (xmmword_180107A60 & 4) != 0 )
    WPP_SF_q(1026, 13, WPP_5ae54466eb4b39fe6c428c9cb8d9284a_Traceguids);
  SetLastError(IsValid);
  return v31;
}

```

## disassembly

```asm
0x18004763c  push    rbp
0x18004763e  push    rbx
0x18004763f  push    rsi
0x180047640  push    rdi
0x180047641  push    r12
0x180047643  push    r13
0x180047645  push    r14
0x180047647  push    r15
0x180047649  lea     rbp, [rsp-7]
0x18004764e  sub     rsp, 0B8h
0x180047655  mov     rax, cs:__security_cookie
0x18004765c  xor     rax, rsp
0x18004765f  mov     [rbp+3Fh+var_50], rax
0x180047663  mov     rax, [rbp+3Fh+arg_28]
0x180047667  mov     r13, r9
0x18004766a  mov     rdi, [rbp+3Fh+arg_20]
0x18004766e  mov     r12, r8
0x180047671  mov     [rbp+3Fh+var_88], rax
0x180047675  mov     rbx, rdx
0x180047678  mov     r14, rcx
0x18004767b  mov     [rbp+3Fh+var_60], rdx
0x18004767f  test    byte ptr cs:xmmword_180107A60, 4
0x180047686  jnz     loc_180047ACE
0x18004768c  xor     r10d, r10d
0x18004768f  mov     [rbp+3Fh+var_68], r10
0x180047693  mov     esi, r10d
0x180047696  mov     [rbp+3Fh+var_78], r10
0x18004769a  mov     [rbp+3Fh+var_80], r10
0x18004769e  mov     [rbp+3Fh+var_8C], r10d
0x1800476a2  mov     [rbp+3Fh+var_58], r10d
0x1800476a6  test    rbx, rbx
0x1800476a9  jz      loc_180047AFD
0x1800476af  mov     [rbp+3Fh+var_90], 1
0x1800476b6  cmp     [rbx], r10w
0x1800476ba  jz      loc_180047AFD
0x1800476c0  cmp     cs:?GlobalDataInitialized@@3HA, r10d; int GlobalDataInitialized
0x1800476c7  jz      loc_180047B11
0x1800476cd  xor     r8d, r8d; int
0x1800476d0  lea     rdx, [rbp+3Fh+var_68]; void **
0x1800476d4  mov     rcx, r14; void *
0x1800476d7  call    ?MapHandleToAddress@@YAKPEAXPEAPEAXH@Z; MapHandleToAddress(void *,void * *,int)
0x1800476dc  mov     ebx, eax
0x1800476de  test    eax, eax
0x1800476e0  jnz     loc_180047928
0x1800476e6  mov     rcx, [rbp+3Fh+var_68]
0x1800476ea  mov     edx, 6E6F4348h
0x1800476ef  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x1800476f4  mov     ebx, eax
0x1800476f6  test    eax, eax
0x1800476f8  jnz     loc_180047912
0x1800476fe  mov     esi, [rbp+3Fh+arg_30]
0x180047701  test    esi, 0FF7FFC33h
0x180047707  jnz     loc_180047B6E
0x18004770d  lea     rdx, [rbp+3Fh+var_8C]
0x180047711  lea     rcx, [rbp+3Fh+var_60]
0x180047715  call    ParseVerb
0x18004771a  mov     ebx, eax
0x18004771c  test    eax, eax
0x18004771e  jnz     loc_180047928
0x180047724  lea     rdx, [rbp+3Fh+var_80]
0x180047728  mov     rcx, r13
0x18004772b  call    ParseHttpVersion
0x180047730  mov     ebx, eax
0x180047732  test    eax, eax
0x180047734  jnz     loc_180047928
0x18004773a  test    rdi, rdi
0x18004773d  jnz     loc_180047B1B
0x180047743  mov     rbx, [rbp+3Fh+var_68]
0x180047747  mov     [rbp+3Fh+var_70], rbx
0x18004774b  movzx   r14d, word ptr [rbx+19Ch]
0x180047753  movzx   ecx, r14w; unsigned __int16
0x180047757  call    ?IsInappropriateHTTPPort@@YAHG@Z; IsInappropriateHTTPPort(ushort)
0x18004775c  test    eax, eax
0x18004775e  jnz     loc_180047B2C
0x180047764  mov     rcx, rbx; struct HANDLE_OBJECT *
0x180047767  call    ?GetRootHandle@@YAPEAVINTERNET_SESSION_HANDLE_OBJECT@@PEAVHANDLE_OBJECT@@@Z; GetRootHandle(HANDLE_OBJECT *)
0x18004776c  mov     r15d, esi
0x18004776f  xor     r10d, r10d
0x180047772  and     r15d, 800000h
0x180047779  cmp     [rax+25Ch], r10d
0x180047780  jnz     loc_180047B36
0x180047786  cmp     [rbx+1A4h], r10d
0x18004778d  jnz     loc_180047B48
0x180047793  mov     r13, [rbp+3Fh+var_88]
0x180047797  mov     rcx, [rbp+3Fh+var_68]; struct INTERNET_CONNECT_HANDLE_OBJECT *
0x18004779b  lea     rdx, [rbp+3Fh+var_78]; void **
0x18004779f  mov     r8d, esi
0x1800477a2  btr     r8d, 15h; unsigned int
0x1800477a7  call    ?RMakeHttpReqObjectHandle@@YAKPEAXPEAPEAXK@Z; RMakeHttpReqObjectHandle(void *,void * *,ulong)
0x1800477ac  mov     rsi, [rbp+3Fh+var_78]
0x1800477b0  xor     r10d, r10d
0x1800477b3  mov     ebx, eax
0x1800477b5  test    eax, eax
0x1800477b7  jnz     loc_180047912
0x1800477bd  test    r14w, r14w
0x1800477c1  jz      loc_180047B78
0x1800477c7  mov     [rsi+19Ch], r14w
0x1800477cf  lea     rcx, [rsi+308h]; this
0x1800477d6  mov     r8d, [rbp+3Fh+var_8C]; unsigned int
0x1800477da  xor     r9d, r9d; unsigned int
0x1800477dd  mov     rdx, [rbp+3Fh+var_60]; unsigned __int16 *
0x1800477e1  mov     dword ptr [rsp+0F0h+var_D0], r10d; char
0x1800477e6  call    ?SetStringW@CAnsiString@@QEAAKPEBGKIH@Z; CAnsiString::SetStringW(ushort const *,ulong,uint,int)
0x1800477eb  xor     r10d, r10d
0x1800477ee  mov     ebx, eax
0x1800477f0  test    eax, eax
0x1800477f2  jnz     loc_180047912
0x1800477f8  test    r15d, r15d
0x1800477fb  mov     rcx, rsi
0x1800477fe  cmovnz  rcx, rsi
0x180047802  neg     r15d
0x180047805  sbb     eax, eax
0x180047807  neg     eax
0x180047809  inc     eax
0x18004780b  mov     [rcx+1A0h], eax
0x180047811  mov     ecx, 7FFFFFFFh
0x180047816  test    r12, r12
0x180047819  jz      loc_180047953
0x18004781f  cmp     [r12], r10w
0x180047824  jz      loc_180047953
0x18004782a  mov     dword ptr [rbp+3Fh+var_88+4], r10d
0x18004782e  mov     edx, ecx
0x180047830  mov     [rbp+3Fh+var_58], r10d
0x180047834  mov     rax, r12
0x180047837  cmp     [rax], r10w
0x18004783b  jz      short loc_180047847
0x18004783d  add     rax, 2
0x180047841  sub     rdx, 1
0x180047845  jnz     short loc_180047837
0x180047847  mov     rax, rdx
0x18004784a  neg     rax
0x18004784d  mov     rax, rdx
0x180047850  sbb     r8d, r8d
0x180047853  sub     rcx, rdx
0x180047856  not     r8d
0x180047859  and     r8d, 80070057h
0x180047860  neg     rax
0x180047863  sbb     r14, r14
0x180047866  and     r14, rcx
0x180047869  test    rdx, rdx
0x18004786c  jz      loc_180047B91
0x180047872  mov     [rbp+3Fh+var_58], r14d
0x180047876  mov     ecx, r8d
0x180047879  call    WX_WIN32_FROM_HR
0x18004787e  mov     ebx, eax
0x180047880  test    eax, eax
0x180047882  jnz     loc_180047912
0x180047888  mov     r15d, [rbp+3Fh+arg_30]
0x18004788c  mov     r8d, r14d; unsigned int
0x18004788f  mov     r9d, r15d; unsigned int
0x180047892  mov     rdx, r12; unsigned __int16 *
0x180047895  mov     rcx, rsi; this
0x180047898  call    ?SetPath@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKPEBGKK@Z; HTTP_REQUEST_HANDLE_OBJECT::SetPath(ushort const *,ulong,ulong)
0x18004789d  mov     ebx, eax
0x18004789f  test    eax, eax
0x1800478a1  jnz     short loc_180047912
0x1800478a3  mov     eax, dword ptr [rbp+3Fh+var_80]
0x1800478a6  lea     r14, [rsi+2C8h]
0x1800478ad  mov     [rsi+300h], eax
0x1800478b3  mov     rcx, r14; lpCriticalSection
0x1800478b6  mov     eax, dword ptr [rbp+3Fh+var_80+4]
0x1800478b9  mov     [rsi+304h], eax
0x1800478bf  call    cs:__imp_EnterCriticalSection
0x1800478c5  xor     r10d, r10d
0x1800478c8  test    rdi, rdi
0x1800478cb  jnz     loc_18004797B
0x1800478d1  test    r13, r13
0x1800478d4  jnz     loc_180047BAB
0x1800478da  mov     rcx, r14; lpCriticalSection
0x1800478dd  call    cs:__imp_LeaveCriticalSection
0x1800478e3  mov     rcx, rsi
0x1800478e6  call    ?SetState@HTTP_REQUEST_HANDLE_OBJECT@@QEAAXW4HTTPREQ_STATE@@@Z; HTTP_REQUEST_HANDLE_OBJECT::SetState(HTTPREQ_STATE)
0x1800478eb  mov     dword ptr [rsi+338h], 0
0x1800478f5  bt      r15d, 15h
0x1800478fa  jb      loc_180047C25
0x180047900  mov     rcx, rsi; this
0x180047903  call    ?UpdateURL@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKXZ; HTTP_REQUEST_HANDLE_OBJECT::UpdateURL(void)
0x180047908  mov     ebx, eax
0x18004790a  test    eax, eax
0x18004790c  jz      loc_1800479B9
0x180047912  test    rsi, rsi
0x180047915  jz      short loc_180047928
0x180047917  mov     rcx, rsi; this
0x18004791a  call    ?Dereference@HANDLE_OBJECT@@QEAAHXZ; HANDLE_OBJECT::Dereference(void)
0x18004791f  mov     rcx, [rsi+20h]; hInternet
0x180047923  call    WinHttpCloseHandle
0x180047928  test    byte ptr cs:xmmword_180107A50, 2
0x18004792f  jz      loc_180047ABF
0x180047935  mov     edx, 0Ch
0x18004793a  lea     r8, WPP_5ae54466eb4b39fe6c428c9cb8d9284a_Traceguids
0x180047941  mov     ecx, 201h
0x180047946  mov     r9d, ebx
0x180047949  call    WPP_SF_d
0x18004794e  jmp     loc_180047ABF
0x180047953  mov     r9d, 40h ; '@'; unsigned int
0x180047959  lea     rdx, pwszObjectName; "/"
0x180047960  mov     rcx, rsi; this
0x180047963  lea     r8d, [r9-3Fh]; unsigned int
0x180047967  call    ?SetPath@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKPEBGKK@Z; HTTP_REQUEST_HANDLE_OBJECT::SetPath(ushort const *,ulong,ulong)
0x18004796c  mov     ebx, eax
0x18004796e  test    eax, eax
0x180047970  jnz     short loc_180047912
0x180047972  mov     r15d, [rbp+3Fh+arg_30]
0x180047976  jmp     loc_1800478A3
0x18004797b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004797f  inc     r9; unsigned __int16
0x180047982  cmp     [rdi+r9*2], r10w
0x180047987  jnz     short loc_18004797F
0x180047989  cmp     r9, 0FFFFh
0x180047990  ja      loc_180047BA1
0x180047996  mov     r8, rdi; unsigned __int16 *
0x180047999  mov     rcx, rsi; this
0x18004799c  call    ?SetRequestHeader@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKKPEBGGH@Z; HTTP_REQUEST_HANDLE_OBJECT::SetRequestHeader(ulong,ushort const *,ushort,int)
0x1800479a1  mov     ebx, eax
0x1800479a3  test    eax, eax
0x1800479a5  jz      loc_1800478D1
0x1800479ab  mov     rcx, r14; lpCriticalSection
0x1800479ae  call    cs:__imp_LeaveCriticalSection
0x1800479b4  jmp     loc_180047912
0x1800479b9  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800479c0  mov     ebx, 29D0h
0x1800479c5  mov     r8d, ebx; dwBytes
0x1800479c8  xor     edx, edx; dwFlags
0x1800479ca  call    cs:__imp_HeapAlloc
0x1800479d0  mov     rdi, rax
0x1800479d3  test    rax, rax
0x1800479d6  jz      loc_180047AC4
0x1800479dc  mov     r8d, ebx; Size
0x1800479df  xor     edx, edx; Val
0x1800479e1  mov     rcx, rax; void *
0x1800479e4  call    memset_0
0x1800479e9  mov     rcx, [rbp+3Fh+var_70]; struct HANDLE_OBJECT *
0x1800479ed  call    ?GetRootHandle@@YAPEAVINTERNET_SESSION_HANDLE_OBJECT@@PEAVHANDLE_OBJECT@@@Z; GetRootHandle(HANDLE_OBJECT *)
0x1800479f2  mov     rcx, [rbp+3Fh+var_70]; struct HANDLE_OBJECT *
0x1800479f6  mov     ebx, [rax+1C8h]
0x1800479fc  call    ?GetRootHandle@@YAPEAVINTERNET_SESSION_HANDLE_OBJECT@@PEAVHANDLE_OBJECT@@@Z; GetRootHandle(HANDLE_OBJECT *)
0x180047a01  mov     r9d, ebx; unsigned int
0x180047a04  mov     rdx, rsi; struct HTTP_REQUEST_HANDLE_OBJECT *
0x180047a07  mov     rcx, rdi; this
0x180047a0a  mov     r8d, [rax+1C4h]; unsigned int
0x180047a11  call    ??0HTTP_USER_REQUEST@@QEAA@PEAVHTTP_REQUEST_HANDLE_OBJECT@@KK@Z; HTTP_USER_REQUEST::HTTP_USER_REQUEST(HTTP_REQUEST_HANDLE_OBJECT *,ulong,ulong)
0x180047a16  test    rax, rax
0x180047a19  jz      loc_180047AC4
0x180047a1f  mov     rcx, rsi; this
0x180047a22  mov     [rsi+1C0h], rax
0x180047a29  call    ?Dereference@HANDLE_OBJECT@@QEAAHXZ; HANDLE_OBJECT::Dereference(void)
0x180047a2e  test    eax, eax
0x180047a30  jnz     loc_180047ABA
0x180047a36  mov     r14, [rsi+20h]
0x180047a3a  lea     edi, [rax+1]
0x180047a3d  lock xadd cs:?g_dwActivityIdCount@@3KC, edi; ulong volatile g_dwActivityIdCount
0x180047a45  inc     edi
0x180047a47  call    cs:__imp_GetCurrentProcessId
0x180047a4d  mov     ebx, eax
0x180047a4f  call    cs:__imp_GetCurrentThreadId
0x180047a55  shl     eax, 10h
0x180047a58  xor     eax, ebx
0x180047a5a  mov     [rsi+0B8h], r14d
0x180047a61  mov     [rsi+0C0h], eax
0x180047a67  xor     ebx, ebx
0x180047a69  mov     [rsi+0BCh], edi
0x180047a6f  mov     [rsi+0C4h], esi
0x180047a75  mov     rcx, [rbp+3Fh+var_68]; void *
0x180047a79  test    rcx, rcx
0x180047a7c  jnz     loc_180047C39
0x180047a82  test    byte ptr cs:xmmword_180107A60, 4
0x180047a89  jnz     loc_180047C4B
0x180047a8f  mov     ecx, ebx; dwErrCode
0x180047a91  call    cs:__imp_SetLastError
0x180047a97  mov     rax, r14
0x180047a9a  mov     rcx, [rbp+3Fh+var_50]
0x180047a9e  xor     rcx, rsp; StackCookie
0x180047aa1  call    __security_check_cookie
0x180047aa6  add     rsp, 0B8h
0x180047aad  pop     r15
0x180047aaf  pop     r14
0x180047ab1  pop     r13
0x180047ab3  pop     r12
0x180047ab5  pop     rdi
0x180047ab6  pop     rsi
0x180047ab7  pop     rbx
0x180047ab8  pop     rbp
0x180047ab9  retn
0x180047aba  mov     ebx, 2EF1h
0x180047abf  xor     r14d, r14d
0x180047ac2  jmp     short loc_180047A75
0x180047ac4  mov     ebx, 8
0x180047ac9  jmp     loc_180047912
0x180047ace  mov     r15d, [rbp+3Fh+arg_30]
0x180047ad2  mov     r9, r14
0x180047ad5  mov     [rsp+0F0h+var_A8], r15d
0x180047ada  mov     [rsp+0F0h+var_B0], rax
0x180047adf  mov     [rsp+0F0h+var_B8], rdi
0x180047ae4  mov     [rsp+0F0h+var_C0], r13
0x180047ae9  mov     [rsp+0F0h+var_C8], r12
0x180047aee  mov     qword ptr [rsp+0F0h+var_D0], rbx
0x180047af3  call    WPP_SF_qSSSSqDP
0x180047af8  jmp     loc_18004768C
0x180047afd  lea     rax, pwszVerb; "GET"
0x180047b04  mov     [rbp+3Fh+var_90], r10d
  ... truncated ...
```
