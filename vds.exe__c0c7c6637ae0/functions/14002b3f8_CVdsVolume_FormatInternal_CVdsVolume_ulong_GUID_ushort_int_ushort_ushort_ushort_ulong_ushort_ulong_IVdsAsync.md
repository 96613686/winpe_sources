# CVdsVolume::FormatInternal(CVdsVolume *,ulong *,_GUID,ushort *,int,ushort *,ushort *,ushort,ulong,ushort *,ulong,IVdsAsync * *)

- ea: `0x14002b3f8`
- end: `0x14002ba6c`
- name: `?FormatInternal@CVdsVolume@@SAJPEAV1@PEAKU_GUID@@PEAGH33GK3KPEAPEAUIVdsAsync@@@Z`
- size: `1652`
- prototype: `__int64 __fastcall(struct CVdsVolume *, unsigned int *, struct _GUID *, unsigned __int16 *, int, unsigned __int16 *, wchar_t *String1, unsigned __int16, unsigned int, unsigned __int16 *, unsigned int, struct IVdsAsync **)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140041710`
- `0x140045df0`

## callees

- `0x140005b1c`
- `0x140006e60`
- `0x140012c9c`
- `0x14002b3f8`
- `0x140040d6c`
- `0x140042b30`
- `0x14004353c`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14002b53e`
- `msvcrt!_wcsicmp` at `0x14002b56c`
- `msvcrt!_wcsicmp` at `0x14002b59d`
- `msvcrt!_wcsicmp` at `0x14002b5ce`
- `msvcrt!_wcsicmp` at `0x14002b7cf`
- `msvcrt!_wcsicmp` at `0x14002b53e`
- `msvcrt!_wcsicmp` at `0x14002b56c`
- `msvcrt!_wcsicmp` at `0x14002b59d`
- `msvcrt!_wcsicmp` at `0x14002b5ce`
- `msvcrt!_wcsicmp` at `0x14002b7cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002b761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002b9e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002b761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002b9e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002b6b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002b708`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002b9f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002b6b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002b708`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002b9f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b98d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14002b919`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14002b919`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b77b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002ba19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002b77b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002ba19`
- `vdsutil!OpenDevice` at `0x14002b635`
- `vdsutil!OpenDevice` at `0x14002b635`
- `vdsutil!VdsHeapAlloc` at `0x14002b6cb`
- `vdsutil!VdsHeapAlloc` at `0x14002b6cb`
- `vdsutil!VdsHeapFree` at `0x14002b716`
- `vdsutil!VdsHeapFree` at `0x14002ba02`
- `vdsutil!VdsHeapFree` at `0x14002b716`
- `vdsutil!VdsHeapFree` at `0x14002ba02`
- `vdsutil!VdsTraceEx` at `0x14002b506`
- `vdsutil!VdsTraceEx` at `0x14002b653`
- `vdsutil!VdsTraceEx` at `0x14002b7aa`
- `vdsutil!VdsTraceEx` at `0x14002b9d1`
- `vdsutil!VdsTraceEx` at `0x14002b506`
- `vdsutil!VdsTraceEx` at `0x14002b653`
- `vdsutil!VdsTraceEx` at `0x14002b7aa`
- `vdsutil!VdsTraceEx` at `0x14002b9d1`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002b49a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002b622`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002b49a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14002b622`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002b78d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002ba3a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002b78d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14002ba3a`
- `vdsutil!VdsTraceW` at `0x14002b753`
- `vdsutil!VdsTraceW` at `0x14002b7ed`
- `vdsutil!VdsTraceW` at `0x14002b753`
- `vdsutil!VdsTraceW` at `0x14002b7ed`

## string_xrefs

- `0x14002b9a2`: `CVdsVolume::FormatInternal, 13, path=%s, hr=%lX`
- `0x14002b79e`: `CVdsVolume::FormatInternal, 8, path=%s, error=%lX`
- `0x14002b7de`: `CVdsVolume::FormatInternal, 9, path=%s, hr=%lX`
- `0x14002b817`: `CVdsVolume::FormatInternal, 10, path=%s, hr=%lX`
- `0x14002b83d`: `CVdsVolume::FormatInternal, 11, path=%s, hr=%lX`
- `0x14002b8dd`: `CVdsVolume::FormatInternal, 12, path=%s, hr=%lX`
- `0x14002b956`: `CVdsVolume::FormatInternal, 14, path=%s, hr=%lx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsVolume::FormatInternal(
        struct CVdsVolume *a1,
        unsigned int *a2,
        struct _GUID *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 *a6,
        wchar_t *String1,
        unsigned __int16 a8,
        unsigned int a9,
        unsigned __int16 *a10,
        char a11,
        struct IVdsAsync **a12)
{
  wchar_t *v14; // rsi
  char *v15; // r13
  int v16; // eax
  signed int v17; // ebx
  signed int v18; // eax
  int v19; // eax
  char *v20; // r14
  int i; // ecx
  __int64 v22; // r15
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v24; // rax
  HANDLE v25; // rax
  const wchar_t *v26; // rdx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  signed int LastError; // eax
  HANDLE v32; // rax
  char v34; // [rsp+80h] [rbp-80h]
  char v35; // [rsp+81h] [rbp-7Fh]
  __int64 v36; // [rsp+88h] [rbp-78h] BYREF
  int v37; // [rsp+90h] [rbp-70h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp-68h] BYREF
  DWORD ThreadId; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int *v42; // [rsp+B8h] [rbp-48h]
  LPVOID lpParameter[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v44; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v45; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v46; // [rsp+E8h] [rbp-18h]
  struct CVdsVolume *v47; // [rsp+F0h] [rbp-10h]
  _BYTE v48[16]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v49[16]; // [rsp+108h] [rbp+8h] BYREF
  __int128 v50; // [rsp+118h] [rbp+18h] BYREF
  __int128 v51; // [rsp+128h] [rbp+28h]
  __int128 v52; // [rsp+138h] [rbp+38h]
  LPVOID v53; // [rsp+148h] [rbp+48h]

  v46 = a4;
  *(_QWORD *)&v44 = a3;
  v42 = a2;
  v47 = a1;
  v14 = String1;
  v45 = a10;
  ThreadId = 0;
  v15 = 0;
  v34 = 0;
  v35 = 0;
  lpParameter[0] = 0;
  v36 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v40 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v49, 0x5Eu, "CVdsVolume::FormatInternal()");
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  if ( a4 && a6 && a12 )
  {
    *a12 = 0;
    if ( a1 )
    {
      v16 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)a1 + 16) + 24LL))(*((_QWORD *)a1 + 16), &v50);
      v17 = v16;
      if ( v16 < 0 )
      {
        VdsTraceEx(94, 0, "CVdsVolume::FormatInternal, 2, hr=%lX", (unsigned int)v16);
        goto LABEL_66;
      }
      if ( (WORD4(v52) & 0x2000) != 0 )
      {
        v17 = -2147210985;
        VdsTraceEx(94, 0, "CVdsVolume::FormatInternal, 3, hr=%lX", 2147756311LL);
        goto LABEL_66;
      }
    }
    if ( String1 )
    {
      if ( !_wcsicmp(String1, L"NTFS") && (WORD4(v52) & 0x4000) != 0 )
      {
        v17 = -2147210988;
        VdsTraceEx(94, 0, "CVdsVolume::FormatInternal, 4, hr=%lX", 2147756308LL);
        goto LABEL_66;
      }
      if ( !_wcsicmp(String1, L"FAT32") && (WORD4(v52) & 0x8000) != 0 )
      {
        v17 = -2147210987;
        VdsTraceEx(94, 0, "CVdsVolume::FormatInternal, 5, hr=%lX", 2147756309LL);
        goto LABEL_66;
      }
      if ( !_wcsicmp(String1, L"FAT") && (DWORD2(v52) & 0x10000) != 0 )
      {
        v17 = -2147210986;
        VdsTraceEx(94, 0, "CVdsVolume::FormatInternal, 6, hr=%lX", 2147756310LL);
        goto LABEL_66;
      }
      if ( !_wcsicmp(String1, L"ReFS") && (DWORD2(v52) & 0x800000) != 0 )
      {
        v17 = -2147210746;
        VdsTraceEx(94, 0, "CVdsVolume::FormatInternal, 7, hr=%lX", 2147756550LL);
        goto LABEL_66;
      }
    }
    else
    {
      hObject = 0;
      v37 = 0;
      pv = 0;
      CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v48, 0x5Eu, "CVdsVolume::GetFSType()");
      v18 = OpenDevice(a6, 3221225472LL, &hObject);
      v17 = v18;
      if ( v18 )
      {
        VdsTraceEx(94, 1, "CVdsVolume::GetFSType, 2, error=%ld", v18);
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
      }
      else
      {
        v19 = CVdsVolume::QueryFileSystemFormatSupportInternal(
                hObject,
                (struct _VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP **)&pv,
                &v37);
        v17 = v19;
        v20 = (char *)pv;
        if ( v19 >= 0 )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= v37 )
              goto LABEL_38;
            v22 = 204LL * i;
            if ( (*((_BYTE *)pv + v22) & 1) != 0 )
              break;
          }
          ProcessHeap = GetProcessHeap();
          v24 = (unsigned __int16 *)VdsHeapAlloc(ProcessHeap, 8, 64);
          v14 = v24;
          if ( !v24 )
          {
            v17 = -2147024882;
            VdsTraceW(0, L"CVdsVolume::GetFSType, 4, hr=%lX", 2147942414LL);
            goto LABEL_40;
          }
          v34 = 1;
          v17 = StringCchCopyW(v24, 0x20u, (const unsigned __int16 *)&v20[v22 + 140]);
          if ( v17 < 0 )
          {
            v25 = GetProcessHeap();
            VdsHeapFree(v25, 0, v14);
            v14 = 0;
            VdsTraceW(0, L"CVdsVolume::GetFSType, 5, hr=%lX", (unsigned int)v17);
            goto LABEL_40;
          }
          if ( !a9 )
            a9 = *(_DWORD *)&v20[v22 + 8];
          if ( !*v14 )
          {
LABEL_38:
            v17 = -2147211885;
            VdsTraceW(0, L"CVdsVolume::GetFSType, 6, hr=%lX", 2147755411LL);
          }
        }
        else
        {
          VdsTraceW(0, L"CVdsVolume::GetFSType, 3, hr=%lX", (unsigned int)v19);
        }
LABEL_40:
        if ( v20 )
          CoTaskMemFree(v20);
      }
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v48);
      if ( v17 < 0 )
      {
        VdsTraceEx(94, 0, "CVdsVolume::FormatInternal, 8, path=%s, error=%lX", (const char *)a6, v17);
        goto LABEL_66;
      }
    }
    if ( (a11 & 4) != 0 && _wcsicmp(v14, L"NTFS") )
    {
      v17 = -2147210984;
      v26 = L"CVdsVolume::FormatInternal, 9, path=%s, hr=%lX";
LABEL_49:
      VdsTraceW(0, v26, a6, (unsigned int)v17);
      goto LABEL_66;
    }
    if ( v42 && (v27 = CVolumeLock::Lock((CVolumeLock *)&v40, (unsigned __int16 *)v42 + 1), v17 = v27, v27 < 0) )
    {
      VdsTraceW(0, L"CVdsVolume::FormatInternal, 10, path=%s, hr=%lX", a6, (unsigned int)v27);
    }
    else
    {
      v28 = CVdsVolume::CreateAsynchObj(101, 1u, 1, &v36);
      v17 = v28;
      if ( v28 >= 0 )
      {
        v35 = 1;
        v44 = *(_OWORD *)v44;
        v29 = CVdsVolume::SetupFormatThreadParam(
                v47,
                &v44,
                v46,
                a5,
                a6,
                v14,
                a8,
                a9,
                v45,
                a11 & 1,
                a11 & 2,
                a11 & 4,
                a11 & 8,
                v42,
                &v36,
                lpParameter);
        v17 = v29;
        if ( v29 >= 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
          v15 = (char *)CreateThread(
                          0,
                          0,
                          (LPTHREAD_START_ROUTINE)CVdsVolume::FormatRoutine,
                          lpParameter[0],
                          0,
                          &ThreadId);
          if ( (unsigned __int64)(v15 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            LastError = GetLastError();
            v17 = LastError;
            if ( LastError > 0 )
              v17 = (unsigned __int16)LastError | 0x80070000;
            v26 = L"CVdsVolume::FormatInternal, 13, path=%s, hr=%lX";
            goto LABEL_49;
          }
          v40 = 0;
          v30 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IVdsAsync **))v36)(v36, &IID_IVdsAsync, a12);
          v17 = v30;
          if ( v30 >= 0 )
          {
            if ( v36 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
              v36 = 0;
            }
          }
          else
          {
            VdsTraceW(0, L"CVdsVolume::FormatInternal, 14, path=%s, hr=%lx", a6, (unsigned int)v30);
          }
        }
        else
        {
          VdsTraceW(0, L"CVdsVolume::FormatInternal, 12, path=%s, hr=%lX", a6, (unsigned int)v29);
        }
      }
      else
      {
        VdsTraceW(0, L"CVdsVolume::FormatInternal, 11, path=%s, hr=%lX", a6, (unsigned int)v28);
      }
    }
  }
  else
  {
    v17 = -2147024809;
    VdsTraceEx(94, 0, "CVdsVolume::FormatInternal, 1, hr=%lX, Volume=%p, Device=%p, Async=%p", -2147024809, a4, a6, a12);
  }
LABEL_66:
  if ( v53 )
  {
    CoTaskMemFree(v53);
    v53 = 0;
  }
  if ( v34 )
  {
    v32 = GetProcessHeap();
    VdsHeapFree(v32, 0, v14);
  }
  if ( v17 < 0 )
  {
    if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v15);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v49);
  CVolumeLock::~CVolumeLock((CVolumeLock *)&v40);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14002b3f8  push    rbp
0x14002b3fa  push    rbx
0x14002b3fb  push    rsi
0x14002b3fc  push    rdi
0x14002b3fd  push    r12
0x14002b3ff  push    r13
0x14002b401  push    r14
0x14002b403  push    r15
0x14002b405  lea     rbp, [rsp-68h]
0x14002b40a  sub     rsp, 168h
0x14002b411  mov     rax, cs:__security_cookie
0x14002b418  xor     rax, rsp
0x14002b41b  mov     [rbp+0A0h+var_50], rax
0x14002b41f  mov     r14, r9
0x14002b422  mov     [rbp+0A0h+var_B8], r9
0x14002b426  mov     qword ptr [rbp+0A0h+var_D0], r8
0x14002b42a  mov     [rbp+0A0h+var_E8], rdx
0x14002b42e  mov     rbx, rcx
0x14002b431  mov     [rbp+0A0h+var_B0], rcx
0x14002b435  mov     rdi, [rbp+0A0h+arg_28]
0x14002b43c  mov     rsi, [rbp+0A0h+String1]
0x14002b443  mov     rax, [rbp+0A0h+arg_48]
0x14002b44a  mov     [rbp+0A0h+var_C0], rax
0x14002b44e  mov     r12, [rbp+0A0h+arg_58]
0x14002b455  mov     [rbp+0A0h+ThreadId], 0
0x14002b45c  xor     r13d, r13d
0x14002b45f  mov     [rbp+0A0h+var_120], r13b
0x14002b463  mov     [rbp+0A0h+var_11F], r13b
0x14002b467  mov     [rbp+0A0h+lpParameter], r13
0x14002b46b  mov     [rbp+0A0h+var_118], r13
0x14002b46f  xorps   xmm0, xmm0
0x14002b472  xor     eax, eax
0x14002b474  movups  [rbp+0A0h+var_88], xmm0
0x14002b478  movups  [rbp+0A0h+var_78], xmm0
0x14002b47c  movups  [rbp+0A0h+var_68], xmm0
0x14002b480  mov     [rbp+0A0h+var_58], rax
0x14002b484  mov     [rbp+0A0h+var_F8], rax
0x14002b488  lea     r8, aCvdsvolumeForm_7; "CVdsVolume::FormatInternal()"
0x14002b48f  lea     r15d, [r13+5Eh]
0x14002b493  mov     edx, r15d
0x14002b496  lea     rcx, [rbp+0A0h+var_98]
0x14002b49a  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002b4a0  nop
0x14002b4a1  xorps   xmm0, xmm0
0x14002b4a4  xor     eax, eax
0x14002b4a6  movups  [rbp+0A0h+var_88], xmm0
0x14002b4aa  movups  [rbp+0A0h+var_78], xmm0
0x14002b4ae  movups  [rbp+0A0h+var_68], xmm0
0x14002b4b2  mov     [rbp+0A0h+var_58], rax
0x14002b4b6  test    r14, r14
0x14002b4b9  jz      loc_14002B9AE
0x14002b4bf  test    rdi, rdi
0x14002b4c2  jz      loc_14002B9AE
0x14002b4c8  test    r12, r12
0x14002b4cb  jz      loc_14002B9AE
0x14002b4d1  mov     [r12], rax
0x14002b4d5  test    rbx, rbx
0x14002b4d8  jz      short loc_14002B52B
0x14002b4da  mov     rcx, [rbx+80h]
0x14002b4e1  mov     rax, [rcx]
0x14002b4e4  lea     rdx, [rbp+0A0h+var_88]
0x14002b4e8  mov     rax, [rax+18h]
0x14002b4ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b4f1  mov     ebx, eax
0x14002b4f3  test    eax, eax
0x14002b4f5  jns     short loc_14002B511
0x14002b4f7  mov     r9d, eax
0x14002b4fa  lea     r8, aCvdsvolumeForm_32; "CVdsVolume::FormatInternal, 2, hr=%lX"
0x14002b501  xor     edx, edx
0x14002b503  mov     ecx, r15d
0x14002b506  call    cs:__imp_VdsTraceEx
0x14002b50c  jmp     loc_14002B9D7
0x14002b511  test    dword ptr [rbp+0A0h+var_68+8], 2000h
0x14002b518  jz      short loc_14002B52B
0x14002b51a  mov     ebx, 80042917h
0x14002b51f  mov     r9d, ebx
0x14002b522  lea     r8, aCvdsvolumeForm_26; "CVdsVolume::FormatInternal, 3, hr=%lX"
0x14002b529  jmp     short loc_14002B501
0x14002b52b  test    rsi, rsi
0x14002b52e  jz      loc_14002B5FD
0x14002b534  lea     rdx, aNtfs; "NTFS"
0x14002b53b  mov     rcx, rsi; String1
0x14002b53e  call    cs:__imp__wcsicmp
0x14002b544  test    eax, eax
0x14002b546  jnz     short loc_14002B562
0x14002b548  test    dword ptr [rbp+0A0h+var_68+8], 4000h
0x14002b54f  jz      short loc_14002B562
0x14002b551  mov     ebx, 80042914h
0x14002b556  mov     r9d, ebx
0x14002b559  lea     r8, aCvdsvolumeForm_6; "CVdsVolume::FormatInternal, 4, hr=%lX"
0x14002b560  jmp     short loc_14002B501
0x14002b562  lea     rdx, aFat32; "FAT32"
0x14002b569  mov     rcx, rsi; String1
0x14002b56c  call    cs:__imp__wcsicmp
0x14002b572  test    eax, eax
0x14002b574  jnz     short loc_14002B593
0x14002b576  test    dword ptr [rbp+0A0h+var_68+8], 8000h
0x14002b57d  jz      short loc_14002B593
0x14002b57f  mov     ebx, 80042915h
0x14002b584  mov     r9d, ebx
0x14002b587  lea     r8, aCvdsvolumeForm_19; "CVdsVolume::FormatInternal, 5, hr=%lX"
0x14002b58e  jmp     loc_14002B501
0x14002b593  lea     rdx, aFat; "FAT"
0x14002b59a  mov     rcx, rsi; String1
0x14002b59d  call    cs:__imp__wcsicmp
0x14002b5a3  test    eax, eax
0x14002b5a5  jnz     short loc_14002B5C4
0x14002b5a7  test    dword ptr [rbp+0A0h+var_68+8], 10000h
0x14002b5ae  jz      short loc_14002B5C4
0x14002b5b0  mov     ebx, 80042916h
0x14002b5b5  mov     r9d, ebx
0x14002b5b8  lea     r8, aCvdsvolumeForm_21; "CVdsVolume::FormatInternal, 6, hr=%lX"
0x14002b5bf  jmp     loc_14002B501
0x14002b5c4  lea     rdx, aRefs_0; "ReFS"
0x14002b5cb  mov     rcx, rsi; String1
0x14002b5ce  call    cs:__imp__wcsicmp
0x14002b5d4  test    eax, eax
0x14002b5d6  jnz     loc_14002B7B5
0x14002b5dc  test    dword ptr [rbp+0A0h+var_68+8], 800000h
0x14002b5e3  jz      loc_14002B7B5
0x14002b5e9  mov     ebx, 80042A06h
0x14002b5ee  mov     r9d, ebx
0x14002b5f1  lea     r8, aCvdsvolumeForm_8; "CVdsVolume::FormatInternal, 7, hr=%lX"
0x14002b5f8  jmp     loc_14002B501
0x14002b5fd  mov     [rbp+0A0h+hObject], 0
0x14002b605  mov     [rbp+0A0h+var_110], 0
0x14002b60c  mov     [rbp+0A0h+pv], 0
0x14002b614  lea     r8, aCvdsvolumeGetf_4; "CVdsVolume::GetFSType()"
0x14002b61b  mov     edx, r15d
0x14002b61e  lea     rcx, [rbp+0A0h+var_A8]
0x14002b622  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14002b628  nop
0x14002b629  lea     r8, [rbp+0A0h+hObject]
0x14002b62d  mov     edx, 0C0000000h
0x14002b632  mov     rcx, rdi
0x14002b635  call    cs:__imp_OpenDevice
0x14002b63b  mov     ebx, eax
0x14002b63d  test    eax, eax
0x14002b63f  jz      short loc_14002B66F
0x14002b641  mov     r9d, eax
0x14002b644  lea     r8, aCvdsvolumeGetf_26; "CVdsVolume::GetFSType, 2, error=%ld"
0x14002b64b  mov     edx, 1
0x14002b650  mov     ecx, r15d
0x14002b653  call    cs:__imp_VdsTraceEx
0x14002b659  test    ebx, ebx
0x14002b65b  jle     loc_14002B76D
0x14002b661  movzx   ebx, bx
0x14002b664  or      ebx, 80070000h
0x14002b66a  jmp     loc_14002B76D
0x14002b66f  lea     r8, [rbp+0A0h+var_110]; int *
0x14002b673  lea     rdx, [rbp+0A0h+pv]; struct _VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP **
0x14002b677  mov     rcx, [rbp+0A0h+hObject]; void *
0x14002b67b  call    ?QueryFileSystemFormatSupportInternal@CVdsVolume@@SAJPEAXPEAPEAU_VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP@@PEAJ@Z; CVdsVolume::QueryFileSystemFormatSupportInternal(void *,_VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP * *,long *)
0x14002b680  mov     ebx, eax
0x14002b682  mov     r14, [rbp+0A0h+pv]
0x14002b686  test    eax, eax
0x14002b688  jns     short loc_14002B699
0x14002b68a  mov     r8d, eax
0x14002b68d  lea     rdx, aCvdsvolumeGetf_27; "CVdsVolume::GetFSType, 3, hr=%lX"
0x14002b694  jmp     loc_14002B751
0x14002b699  xor     ecx, ecx
0x14002b69b  cmp     ecx, [rbp+0A0h+var_110]
0x14002b69e  jge     loc_14002B742
0x14002b6a4  movsxd  rax, ecx
0x14002b6a7  imul    r15, rax, 0CCh
0x14002b6ae  test    byte ptr [r15+r14], 1
0x14002b6b3  jnz     short loc_14002B6B9
0x14002b6b5  inc     ecx
0x14002b6b7  jmp     short loc_14002B69B
0x14002b6b9  call    cs:__imp_GetProcessHeap
0x14002b6bf  mov     rcx, rax
0x14002b6c2  mov     edx, 8
0x14002b6c7  lea     r8d, [rdx+38h]
0x14002b6cb  call    cs:__imp_VdsHeapAlloc
0x14002b6d1  mov     rsi, rax
0x14002b6d4  test    rax, rax
0x14002b6d7  jnz     short loc_14002B6E7
0x14002b6d9  mov     ebx, 8007000Eh
0x14002b6de  lea     rdx, aCvdsvolumeGetf_23; "CVdsVolume::GetFSType, 4, hr=%lX"
0x14002b6e5  jmp     short loc_14002B74E
0x14002b6e7  mov     [rbp+0A0h+var_120], 1
0x14002b6eb  lea     r8, [r14+8Ch]
0x14002b6f2  add     r8, r15; unsigned __int16 *
0x14002b6f5  mov     edx, 20h ; ' '; unsigned __int64
0x14002b6fa  mov     rcx, rsi; unsigned __int16 *
0x14002b6fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002b702  mov     ebx, eax
0x14002b704  test    eax, eax
0x14002b706  jns     short loc_14002B727
0x14002b708  call    cs:__imp_GetProcessHeap
0x14002b70e  mov     r8, rsi
0x14002b711  xor     edx, edx
0x14002b713  mov     rcx, rax
0x14002b716  call    cs:__imp_VdsHeapFree
0x14002b71c  xor     esi, esi
0x14002b71e  lea     rdx, aCvdsvolumeGetf_30; "CVdsVolume::GetFSType, 5, hr=%lX"
0x14002b725  jmp     short loc_14002B74E
0x14002b727  cmp     [rbp+0A0h+arg_40], 0
0x14002b72e  jnz     short loc_14002B73B
0x14002b730  mov     eax, [r15+r14+8]
0x14002b735  mov     [rbp+0A0h+arg_40], eax
0x14002b73b  xor     eax, eax
0x14002b73d  cmp     ax, [rsi]
0x14002b740  jnz     short loc_14002B759
0x14002b742  mov     ebx, 80042593h
0x14002b747  lea     rdx, aCvdsvolumeGetf_15; "CVdsVolume::GetFSType, 6, hr=%lX"
0x14002b74e  mov     r8d, ebx
0x14002b751  xor     ecx, ecx
0x14002b753  call    cs:__imp_VdsTraceW
0x14002b759  test    r14, r14
0x14002b75c  jz      short loc_14002B767
0x14002b75e  mov     rcx, r14; pv
0x14002b761  call    cs:__imp_CoTaskMemFree
0x14002b767  mov     r15d, 5Eh ; '^'
0x14002b76d  mov     rcx, [rbp+0A0h+hObject]; hObject
0x14002b771  lea     rax, [rcx-1]
0x14002b775  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002b779  ja      short loc_14002B789
0x14002b77b  call    cs:__imp_CloseHandle
0x14002b781  mov     [rbp+0A0h+hObject], 0
0x14002b789  lea     rcx, [rbp+0A0h+var_A8]
0x14002b78d  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002b793  test    ebx, ebx
0x14002b795  jns     short loc_14002B7B5
0x14002b797  mov     [rsp+1A0h+dwCreationFlags], ebx
0x14002b79b  mov     r9, rdi
0x14002b79e  lea     r8, aCvdsvolumeForm_16; "CVdsVolume::FormatInternal, 8, path=%s,"...
0x14002b7a5  xor     edx, edx
0x14002b7a7  mov     ecx, r15d
0x14002b7aa  call    cs:__imp_VdsTraceEx
0x14002b7b0  jmp     loc_14002B9D7
0x14002b7b5  mov     r14d, dword ptr [rbp+0A0h+arg_50]
0x14002b7bc  mov     r15d, r14d
0x14002b7bf  and     r15d, 4
0x14002b7c3  jz      short loc_14002B7F8
0x14002b7c5  lea     rdx, aNtfs; "NTFS"
0x14002b7cc  mov     rcx, rsi; String1
0x14002b7cf  call    cs:__imp__wcsicmp
0x14002b7d5  test    eax, eax
0x14002b7d7  jz      short loc_14002B7F8
0x14002b7d9  mov     ebx, 80042918h
0x14002b7de  lea     rdx, aCvdsvolumeForm_20; "CVdsVolume::FormatInternal, 9, path=%s,"...
0x14002b7e5  mov     r9d, ebx
0x14002b7e8  mov     r8, rdi
0x14002b7eb  xor     ecx, ecx
0x14002b7ed  call    cs:__imp_VdsTraceW
0x14002b7f3  jmp     loc_14002B9D7
0x14002b7f8  mov     rax, [rbp+0A0h+var_E8]
0x14002b7fc  test    rax, rax
0x14002b7ff  jz      short loc_14002B820
0x14002b801  lea     rdx, [rax+2]; unsigned __int16 *
0x14002b805  lea     rcx, [rbp+0A0h+var_F8]; this
0x14002b809  call    ?Lock@CVolumeLock@@QEAAJPEAG@Z; CVolumeLock::Lock(ushort *)
0x14002b80e  mov     ebx, eax
0x14002b810  test    eax, eax
0x14002b812  jns     short loc_14002B820
0x14002b814  mov     r9d, eax
0x14002b817  lea     rdx, aCvdsvolumeForm_33; "CVdsVolume::FormatInternal, 10, path=%s"...
0x14002b81e  jmp     short loc_14002B7E8
0x14002b820  lea     r9, [rbp+0A0h+var_118]
0x14002b824  mov     r8b, 1
0x14002b827  mov     dl, r8b
0x14002b82a  mov     ecx, 65h ; 'e'
0x14002b82f  call    ?CreateAsynchObj@CVdsVolume@@SAJW4_VDS_ASYNC_OUTPUT_TYPE@@EEPEAPEAV?$CComObject@VCVdsServiceAsyncObject@@@ATL@@@Z; CVdsVolume::CreateAsynchObj(_VDS_ASYNC_OUTPUT_TYPE,uchar,uchar,ATL::CComObject<CVdsServiceAsyncObject> * *)
0x14002b834  mov     ebx, eax
0x14002b836  test    eax, eax
0x14002b838  jns     short loc_14002B846
0x14002b83a  mov     r9d, eax
0x14002b83d  lea     rdx, aCvdsvolumeForm_30; "CVdsVolume::FormatInternal, 11, path=%s"...
0x14002b844  jmp     short loc_14002B7E8
0x14002b846  mov     [rbp+0A0h+var_11F], 1
0x14002b84a  mov     rax, qword ptr [rbp+0A0h+var_D0]
0x14002b84e  movaps  xmm0, xmmword ptr [rax]
0x14002b851  movdqa  [rbp+0A0h+var_D0], xmm0
0x14002b856  mov     eax, r14d
0x14002b859  and     eax, 8
0x14002b85c  mov     edx, r14d
0x14002b85f  and     edx, 2
0x14002b862  and     r14d, 1
0x14002b866  lea     rcx, [rbp+0A0h+lpParameter]
0x14002b86a  mov     [rsp+1A0h+var_128], rcx
0x14002b86f  lea     rcx, [rbp+0A0h+var_118]
0x14002b873  mov     [rsp+1A0h+var_130], rcx
0x14002b878  mov     r9, [rbp+0A0h+var_E8]
0x14002b87c  mov     [rsp+1A0h+var_138], r9
0x14002b881  mov     [rsp+1A0h+var_140], eax
0x14002b885  mov     [rsp+1A0h+var_148], r15d
0x14002b88a  mov     [rsp+1A0h+var_150], edx
0x14002b88e  mov     [rsp+1A0h+var_158], r14d
0x14002b893  mov     rax, [rbp+0A0h+var_C0]
0x14002b897  mov     [rsp+1A0h+var_160], rax
0x14002b89c  mov     eax, [rbp+0A0h+arg_40]
0x14002b8a2  mov     [rsp+1A0h+var_168], eax
0x14002b8a6  movzx   eax, [rbp+0A0h+arg_38]
0x14002b8ad  mov     word ptr [rsp+1A0h+var_170], ax
0x14002b8b2  mov     [rsp+1A0h+lpThreadId], rsi
0x14002b8b7  mov     qword ptr [rsp+1A0h+dwCreationFlags], rdi
0x14002b8bc  mov     r9d, [rbp+0A0h+arg_20]
0x14002b8c3  mov     r8, [rbp+0A0h+var_B8]
0x14002b8c7  lea     rdx, [rbp+0A0h+var_D0]
  ... truncated ...
```
