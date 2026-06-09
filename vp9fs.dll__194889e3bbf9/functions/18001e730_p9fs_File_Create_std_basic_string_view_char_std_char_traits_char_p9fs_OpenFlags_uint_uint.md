# p9fs::File::Create(std::basic_string_view<char,std::char_traits<char>>,p9fs::OpenFlags,uint,uint)

- ea: `0x18001e730`
- end: `0x18001ea97`
- name: `?Create@File@p9fs@@UEAA?AV?$BasicExpected@UQid@p9fs@@J@util@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@W4OpenFlags@2@II@Z`
- size: `871`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callees

- `0x180004120`
- `0x1800074e0`
- `0x18001d940`
- `0x18001dc10`
- `0x18001e494`
- `0x18001e730`
- `0x18001ec64`
- `0x1800204c8`
- `0x180028fdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ea42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ea42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e775`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e775`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e94b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e9bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e94b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e9bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e92b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e9aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e92b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e9aa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001e943`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001e985`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001e943`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18001e985`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18001e939`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18001e97c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18001e939`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x18001e97c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e9b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e9b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ea23`
- `lxutil!LxUtilFsTruncate` at `0x18001e8c5`
- `lxutil!LxUtilFsTruncate` at `0x18001e8c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall p9fs::File::Create(__int64 a1, __int64 a2, _OWORD *a3, unsigned int a4, __int16 a5, int a6)
{
  RTL_SRWLOCK *v10; // r14
  int v11; // ecx
  int v12; // edx
  const char *v13; // r9
  const char *v14; // r9
  int v15; // eax
  int v16; // ebx
  __int128 v17; // xmm6
  __int64 v18; // r13
  int v19; // eax
  PTP_IO *v20; // rax
  __int64 v21; // rcx
  DWORD LastError; // edi
  struct _TP_IO *v23; // rdi
  DWORD v24; // edi
  PTP_IO hObject; // [rsp+68h] [rbp-A0h]
  char *hObjecta; // [rsp+68h] [rbp-A0h]
  _QWORD v28[3]; // [rsp+70h] [rbp-98h] BYREF
  PTP_IO pio; // [rsp+88h] [rbp-80h]
  PTP_IO pv; // [rsp+90h] [rbp-78h] BYREF
  int v31; // [rsp+A0h] [rbp-68h]
  __int128 v32; // [rsp+A8h] [rbp-60h]
  HANDLE v33; // [rsp+B8h] [rbp-50h] BYREF
  int v34; // [rsp+C0h] [rbp-48h] BYREF
  char v35; // [rsp+C8h] [rbp-40h] BYREF
  int v36; // [rsp+D0h] [rbp-38h]
  __int128 v37; // [rsp+D8h] [rbp-30h]
  HANDLE FileHandle; // [rsp+E8h] [rbp-20h]
  _BYTE v39[8]; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v40[32]; // [rsp+F8h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+180h] [rbp+78h]

  v10 = (RTL_SRWLOCK *)(a1 + 8);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
  if ( (unsigned __int64)(*(_QWORD *)(a1 + 48) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v11 = *(_DWORD *)(*(_QWORD *)(a1 + 72) + 48LL);
    if ( (v11 & 1) != 0 )
    {
      *(_BYTE *)a2 = 0;
      *(_DWORD *)(a2 + 8) = -30;
    }
    else if ( (v11 & 0x80u) == 0 )
    {
      *(_OWORD *)&v28[1] = *a3;
      p9fs::File::ChildPathWithLockHeld(a1, v39, &v28[1]);
      v12 = p9fs::OpenFlagsToAccessMask(a4);
      LODWORD(v28[0]) = v12;
      v34 = 0;
      if ( !v39[0] )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x139,
          (unsigned int)"onecore\\vm\\inc\\expected.h",
          v13);
      *(_OWORD *)&v28[1] = 0u;
      p9fs::File::CreateFile(
        a1,
        (unsigned int)&v35,
        (unsigned int)v40,
        a6,
        a5 & 0xFFF | 0x8000,
        0,
        v12,
        (_DWORD)v13,
        4,
        (__int64)&v28[1],
        (__int64)&v34);
      if ( v35 )
      {
        v16 = v36;
        v31 = v36;
        v17 = v37;
        v32 = v37;
        v18 = (__int64)FileHandle;
        v33 = FileHandle;
        FileHandle = (HANDLE)-1LL;
        if ( (a4 & 0x200) != 0 && (v34 & 1) == 0 && (v19 = LxUtilFsTruncate(v18, 0)) != 0 )
        {
          *(_BYTE *)a2 = 0;
          *(_DWORD *)(a2 + 8) = v19;
        }
        else
        {
          if ( !v39[0] )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x139,
              (unsigned int)"onecore\\vm\\inc\\expected.h",
              v14);
          std::wstring::operator=(a1 + 16, v40);
          v20 = p9fs::CoroutineIoIssuer::CoroutineIoIssuer(&pv, (struct _TP_IO *)v18);
          v28[1] = v20;
          v21 = a1 + 56;
          if ( (PTP_IO *)(a1 + 56) != v20 )
          {
            hObject = *v20;
            pio = *(PTP_IO *)v21;
            if ( pio )
            {
              LastError = GetLastError();
              WaitForThreadpoolIoCallbacks(pio, 0);
              CloseThreadpoolIo(pio);
              SetLastError(LastError);
              v20 = (PTP_IO *)v28[1];
              v21 = a1 + 56;
            }
            *(_QWORD *)v21 = hObject;
            *v20 = 0;
          }
          *(_QWORD *)(v21 + 8) = v20[1];
          v23 = pv;
          if ( pv )
          {
            WaitForThreadpoolIoCallbacks(pv, 0);
            CloseThreadpoolIo(v23);
          }
          if ( (HANDLE *)(a1 + 48) != &v33 )
          {
            hObjecta = *(char **)(a1 + 48);
            if ( (unsigned __int64)(hObjecta - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              v24 = GetLastError();
              CloseHandle(hObjecta);
              SetLastError(v24);
            }
            *(_QWORD *)(a1 + 48) = v18;
            v18 = -1;
          }
          *(_DWORD *)(a1 + 88) = v28[0];
          *(_OWORD *)(a1 + 120) = v17;
          *(_DWORD *)(a1 + 136) = v16;
          *(_BYTE *)(a1 + 113) = 0;
          *(_BYTE *)a2 = 1;
          *(_OWORD *)(a2 + 8) = *(_OWORD *)(a1 + 120);
        }
        if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle((HANDLE)v18);
        if ( v35 && (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(FileHandle);
      }
      else
      {
        v15 = v36;
        *(_BYTE *)a2 = 0;
        *(_DWORD *)(a2 + 8) = v15;
      }
      if ( v39[0] )
        std::wstring::~wstring(v40);
    }
    else
    {
      *(_BYTE *)a2 = 0;
      *(_DWORD *)(a2 + 8) = -13;
    }
  }
  else
  {
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 8) = -22;
  }
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  return a2;
}

```

## disassembly

```asm
0x18001e730  mov     rax, rsp
0x18001e733  push    rbp
0x18001e734  push    rbx
0x18001e735  push    rsi
0x18001e736  push    rdi
0x18001e737  push    r12
0x18001e739  push    r13
0x18001e73b  push    r14
0x18001e73d  push    r15
0x18001e73f  lea     rbp, [rax-78h]
0x18001e743  sub     rsp, 138h
0x18001e74a  movaps  xmmword ptr [rax-58h], xmm6
0x18001e74e  mov     rax, cs:__security_cookie
0x18001e755  xor     rax, rsp
0x18001e758  mov     [rbp+70h+var_60], rax
0x18001e75c  mov     edi, r9d
0x18001e75f  mov     rsi, r8
0x18001e762  mov     r15, rdx
0x18001e765  mov     r12, rcx
0x18001e768  mov     ebx, [rbp+70h+arg_28]
0x18001e76e  lea     r14, [rcx+8]
0x18001e772  mov     rcx, r14; SRWLock
0x18001e775  call    cs:__imp_AcquireSRWLockExclusive
0x18001e77b  mov     [rsp+170h+hObject], r14
0x18001e780  mov     rax, [r12+30h]
0x18001e785  dec     rax
0x18001e788  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e78c  ja      short loc_18001E7A0
0x18001e78e  xor     esi, esi
0x18001e790  mov     [r15], sil
0x18001e793  mov     dword ptr [r15+8], 0FFFFFFEAh
0x18001e79b  jmp     loc_18001EA3A
0x18001e7a0  mov     rax, [r12+48h]
0x18001e7a5  mov     ecx, [rax+30h]
0x18001e7a8  test    cl, 1
0x18001e7ab  jz      short loc_18001E7BF
0x18001e7ad  xor     esi, esi
0x18001e7af  mov     [r15], sil
0x18001e7b2  mov     dword ptr [r15+8], 0FFFFFFE2h
0x18001e7ba  jmp     loc_18001EA3A
0x18001e7bf  test    cl, cl
0x18001e7c1  jns     short loc_18001E7D5
0x18001e7c3  xor     esi, esi
0x18001e7c5  mov     [r15], sil
0x18001e7c8  mov     dword ptr [r15+8], 0FFFFFFF3h
0x18001e7d0  jmp     loc_18001EA3A
0x18001e7d5  movups  xmm0, xmmword ptr [rsi]
0x18001e7d8  movdqu  xmmword ptr [rsp+170h+var_108+8], xmm0
0x18001e7de  lea     r8, [rsp+170h+var_108+8]
0x18001e7e3  lea     rdx, [rbp+70h+var_88]
0x18001e7e7  mov     rcx, r12
0x18001e7ea  call    ?ChildPathWithLockHeld@File@p9fs@@AEAA?AV?$BasicExpected@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@util@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; p9fs::File::ChildPathWithLockHeld(std::string_view)
0x18001e7ef  nop
0x18001e7f0  mov     r9d, edi
0x18001e7f3  shr     r9d, 7
0x18001e7f7  not     r9d
0x18001e7fa  and     r9d, 1
0x18001e7fe  or      r9d, 2
0x18001e802  mov     ecx, edi
0x18001e804  call    ?OpenFlagsToAccessMask@p9fs@@YAKW4OpenFlags@1@@Z; p9fs::OpenFlagsToAccessMask(p9fs::OpenFlags)
0x18001e809  mov     edx, eax
0x18001e80b  mov     dword ptr [rsp+170h+var_108], eax
0x18001e80f  xor     esi, esi
0x18001e811  mov     [rbp+70h+var_B8], esi
0x18001e814  cmp     [rbp+70h+var_88], sil
0x18001e818  setz    al
0x18001e81b  mov     rcx, [rbp+78h]; this
0x18001e81f  test    al, al
0x18001e821  jnz     loc_18001EA85
0x18001e827  mov     qword ptr [rsp+170h+var_108+8], rsi
0x18001e82c  mov     qword ptr [rsp+170h+var_108+10h], rsi
0x18001e831  mov     eax, dword ptr [rbp+70h+arg_20]
0x18001e837  and     eax, 0FFFh
0x18001e83c  bts     eax, 0Fh
0x18001e840  lea     rcx, [rbp+70h+var_B8]
0x18001e844  mov     [rsp+50h], rcx
0x18001e849  lea     rcx, [rsp+170h+var_108+8]
0x18001e84e  mov     [rsp+170h+var_128], rcx
0x18001e853  mov     dword ptr [rsp+170h+var_130], 4
0x18001e85b  mov     [rsp+170h+var_138], r9d
0x18001e860  mov     [rsp+170h+var_140], edx
0x18001e864  mov     qword ptr [rsp+170h+var_148], rsi
0x18001e869  mov     dword ptr [rsp+170h+var_150], eax
0x18001e86d  mov     r9d, ebx
0x18001e870  lea     r8, [rbp+70h+var_80]
0x18001e874  lea     rdx, [rbp+70h+var_B0]
0x18001e878  mov     rcx, r12
0x18001e87b  call    ?CreateFile@File@p9fs@@AEAA?AV?$BasicExpected@V?$tuple@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@UQid@p9fs@@K@std@@J@util@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK_KKKW4OpenFileFlags@42@V?$span@W4byte@gsl@@$0?0@gsl@@PEAW4OpenFileOutputFlags@42@@Z; p9fs::File::CreateFile(std::wstring const &,ulong,ulong,unsigned __int64,ulong,ulong,p9fs::util::OpenFileFlags,gsl::span<gsl::byte,-1>,p9fs::util::OpenFileOutputFlags *)
0x18001e880  nop
0x18001e881  cmp     [rbp+70h+var_B0], sil
0x18001e885  jnz     short loc_18001E896
0x18001e887  mov     eax, [rbp+70h+var_A8]
0x18001e88a  mov     [r15], sil
0x18001e88d  mov     [r15+8], eax
0x18001e891  jmp     loc_18001EA2A
0x18001e896  mov     ebx, [rbp+70h+var_A8]
0x18001e899  mov     [rbp+70h+var_D8], ebx
0x18001e89c  movups  xmm6, [rbp+70h+var_A0]
0x18001e8a0  movups  [rbp+70h+var_D0], xmm6
0x18001e8a4  mov     r13, [rbp+70h+FileHandle]
0x18001e8a8  mov     [rbp+70h+var_C0], r13
0x18001e8ac  mov     [rbp+70h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x18001e8b4  bt      edi, 9
0x18001e8b8  jnb     short loc_18001E8DB
0x18001e8ba  test    byte ptr [rbp+70h+var_B8], 1
0x18001e8be  jnz     short loc_18001E8DB
0x18001e8c0  xor     edx, edx
0x18001e8c2  mov     rcx, r13
0x18001e8c5  call    cs:__imp_LxUtilFsTruncate
0x18001e8cb  test    eax, eax
0x18001e8cd  jz      short loc_18001E8DB
0x18001e8cf  mov     [r15], sil
0x18001e8d2  mov     [r15+8], eax
0x18001e8d6  jmp     loc_18001E9FB
0x18001e8db  cmp     [rbp+70h+var_88], sil
0x18001e8df  setz    al
0x18001e8e2  mov     rcx, [rbp+78h]; this
0x18001e8e6  test    al, al
0x18001e8e8  jnz     loc_18001EA73
0x18001e8ee  lea     rcx, [r12+10h]
0x18001e8f3  lea     rdx, [rbp+70h+var_80]
0x18001e8f7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001e8fc  mov     rdx, r13; FileHandle
0x18001e8ff  lea     rcx, [rbp+70h+pv]; pv
0x18001e903  call    ??0CoroutineIoIssuer@p9fs@@QEAA@PEAX@Z; p9fs::CoroutineIoIssuer::CoroutineIoIssuer(void *)
0x18001e908  mov     qword ptr [rsp+170h+var_108+8], rax
0x18001e90d  lea     rcx, [r12+38h]
0x18001e912  cmp     rcx, rax
0x18001e915  jz      short loc_18001E966
0x18001e917  mov     rdx, [rax]
0x18001e91a  mov     [rsp+170h+hObject], rdx
0x18001e91f  mov     rdx, [rcx]
0x18001e922  mov     [rbp+70h+pio], rdx
0x18001e926  test    rdx, rdx
0x18001e929  jz      short loc_18001E95B
0x18001e92b  call    cs:__imp_GetLastError
0x18001e931  mov     edi, eax
0x18001e933  xor     edx, edx; fCancelPendingCallbacks
0x18001e935  mov     rcx, [rbp+70h+pio]; pio
0x18001e939  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18001e93f  mov     rcx, [rbp+70h+pio]; pio
0x18001e943  call    cs:__imp_CloseThreadpoolIo
0x18001e949  mov     ecx, edi; dwErrCode
0x18001e94b  call    cs:__imp_SetLastError
0x18001e951  mov     rax, qword ptr [rsp+170h+var_108+8]
0x18001e956  lea     rcx, [r12+38h]
0x18001e95b  mov     rdx, [rsp+170h+hObject]
0x18001e960  mov     [rcx], rdx
0x18001e963  mov     [rax], rsi
0x18001e966  mov     rax, [rax+8]
0x18001e96a  mov     [rcx+8], rax
0x18001e96e  mov     rdi, [rbp+70h+pv]
0x18001e972  test    rdi, rdi
0x18001e975  jz      short loc_18001E98B
0x18001e977  xor     edx, edx; fCancelPendingCallbacks
0x18001e979  mov     rcx, rdi; pio
0x18001e97c  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x18001e982  mov     rcx, rdi; pio
0x18001e985  call    cs:__imp_CloseThreadpoolIo
0x18001e98b  lea     rcx, [rbp+70h+var_C0]
0x18001e98f  lea     rax, [r12+30h]
0x18001e994  cmp     rax, rcx
0x18001e997  jz      short loc_18001E9CE
0x18001e999  mov     rax, [rax]
0x18001e99c  mov     [rsp+170h+hObject], rax
0x18001e9a1  dec     rax
0x18001e9a4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e9a8  ja      short loc_18001E9C5
0x18001e9aa  call    cs:__imp_GetLastError
0x18001e9b0  mov     edi, eax
0x18001e9b2  mov     rcx, [rsp+170h+hObject]; hObject
0x18001e9b7  call    cs:__imp_CloseHandle
0x18001e9bd  mov     ecx, edi; dwErrCode
0x18001e9bf  call    cs:__imp_SetLastError
0x18001e9c5  mov     [r12+30h], r13
0x18001e9ca  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001e9ce  mov     eax, dword ptr [rsp+170h+var_108]
0x18001e9d2  mov     [r12+58h], eax
0x18001e9d7  movdqu  xmmword ptr [r12+78h], xmm6
0x18001e9de  mov     [r12+88h], ebx
0x18001e9e6  mov     [r12+71h], sil
0x18001e9eb  mov     byte ptr [r15], 1
0x18001e9ef  movups  xmm0, xmmword ptr [r12+78h]
0x18001e9f5  movdqu  xmmword ptr [r15+8], xmm0
0x18001e9fb  lea     rax, [r13-1]
0x18001e9ff  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ea03  ja      short loc_18001EA0F
0x18001ea05  mov     rcx, r13; hObject
0x18001ea08  call    cs:__imp_CloseHandle
0x18001ea0e  nop
0x18001ea0f  cmp     [rbp+70h+var_B0], sil
0x18001ea13  jz      short loc_18001EA2A
0x18001ea15  mov     rcx, [rbp+70h+FileHandle]; hObject
0x18001ea19  lea     rax, [rcx-1]
0x18001ea1d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ea21  ja      short loc_18001EA2A
0x18001ea23  call    cs:__imp_CloseHandle
0x18001ea29  nop
0x18001ea2a  cmp     [rbp+70h+var_88], sil
0x18001ea2e  jz      short loc_18001EA3A
0x18001ea30  lea     rcx, [rbp+70h+var_80]
0x18001ea34  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ea39  nop
0x18001ea3a  test    r14, r14
0x18001ea3d  jz      short loc_18001EA48
0x18001ea3f  mov     rcx, r14; SRWLock
0x18001ea42  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ea48  mov     rax, r15
0x18001ea4b  mov     rcx, [rbp+70h+var_60]
0x18001ea4f  xor     rcx, rsp; StackCookie
0x18001ea52  call    __security_check_cookie
0x18001ea57  movaps  xmm6, [rsp+170h+var_58+8]
0x18001ea5f  add     rsp, 138h
0x18001ea66  pop     r15
0x18001ea68  pop     r14
0x18001ea6a  pop     r13
0x18001ea6c  pop     r12
0x18001ea6e  pop     rdi
0x18001ea6f  pop     rsi
0x18001ea70  pop     rbx
0x18001ea71  pop     rbp
0x18001ea72  retn
0x18001ea73  lea     r8, aOnecoreVmIncEx; "onecore\\vm\\inc\\expected.h"
0x18001ea7a  mov     edx, 139h; void *
0x18001ea7f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001ea85  lea     r8, aOnecoreVmIncEx; "onecore\\vm\\inc\\expected.h"
0x18001ea8c  mov     edx, 139h; void *
0x18001ea91  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
