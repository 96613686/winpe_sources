# IsDiskEmptyOfFiles(IVdsService *,int,int *)

- ea: `0x180041f90`
- end: `0x180042486`
- name: `?IsDiskEmptyOfFiles@@YAJPEAUIVdsService@@HPEAH@Z`
- size: `1270`
- prototype: `__int64 __fastcall(struct IVdsService *, int, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800244d4`

## callees

- `0x180039424`
- `0x18003d86c`
- `0x1800417a8`
- `0x180041f90`
- `0x18007ec9a`
- `0x18007ed40`
- `0x180081010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180042250`
- `ntdll!RtlFreeHeap` at `0x180042250`
- `ntdll!RtlAllocateHeap` at `0x180042176`
- `ntdll!RtlAllocateHeap` at `0x180042176`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004237d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004237d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800422c9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800422c9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004235c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004235c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180042311`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180042339`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180042311`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180042339`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004239b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004239b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800423a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800423a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004227d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042297`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004227d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042297`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004238c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004238c`

## pseudocode

```c
__int64 __fastcall IsDiskEmptyOfFiles(struct IVdsService *a1, int a2, int *a3)
{
  int *v3; // rsi
  int v6; // r13d
  int Disk; // ebx
  PVOID Heap; // rsi
  int v9; // eax
  const wchar_t *v10; // r14
  int v11; // edi
  __int64 v12; // rbx
  HRESULT v13; // eax
  unsigned __int16 v14; // bx
  HRESULT v15; // eax
  HRESULT v16; // eax
  const WCHAR *v17; // rbx
  signed int LastError; // eax
  bool v19; // sf
  signed int v20; // eax
  bool v21; // sf
  HANDLE FirstFileW; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v25; // [rsp+30h] [rbp-D0h]
  size_t cchDest; // [rsp+40h] [rbp-C0h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  int v32; // [rsp+70h] [rbp-90h] BYREF
  struct IVdsDisk *v33; // [rsp+78h] [rbp-88h] BYREF
  int *v34; // [rsp+80h] [rbp-80h]
  int v35; // [rsp+88h] [rbp-78h] BYREF
  __int128 v36; // [rsp+8Ch] [rbp-74h]
  __int128 v37; // [rsp+9Ch] [rbp-64h]
  _BYTE pszSrc[20]; // [rsp+ACh] [rbp-54h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF

  v34 = a3;
  v29 = 0;
  v3 = a3;
  v33 = 0;
  v30 = 0;
  v28 = 0;
  v31 = 0;
  v35 = 0;
  v32 = 0;
  v36 = 0;
  v37 = 0;
  memset(pszSrc, 0, sizeof(pszSrc));
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a1 || a2 < 0 || !v3 )
    return 2147942487LL;
  v6 = 0;
  Disk = GetDisk(a1, a2, &v33, 0, 0);
  if ( Disk >= 0 )
  {
    Disk = ((__int64 (__fastcall *)(struct IVdsDisk *, __int64 *))v33->lpVtbl->GetPack)(v33, &v31);
    if ( Disk >= 0 )
    {
      Heap = 0;
      Disk = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 40LL))(v31, &v30);
      if ( Disk >= 0 )
      {
        while ( 1 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v30 + 24LL))(
                 v30,
                 1,
                 &v29,
                 &v32);
          Disk = v9;
          if ( v9 < 0 || v9 == 1 )
            goto LABEL_50;
          if ( !v6
            && (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v29)(v29, &IID_IVdsVolume, &v28) >= 0
            && (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 24LL))(v28, &v35) >= 0 )
          {
            break;
          }
LABEL_41:
          if ( *(_QWORD *)&pszSrc[12] )
          {
            CoTaskMemFree(*(LPVOID *)&pszSrc[12]);
            *(_QWORD *)&pszSrc[12] = 0;
          }
          if ( Heap )
          {
            ProcessHeap = GetProcessHeap();
            if ( HeapFree(ProcessHeap, 0, Heap) )
              Heap = 0;
          }
          if ( v28 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            v28 = 0;
          }
          if ( v29 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            v29 = 0;
          }
        }
        v10 = *(const wchar_t **)&pszSrc[12];
        pszDest = 0;
        cchDest = 0;
        if ( *(_QWORD *)&pszSrc[12] )
        {
          v11 = 0;
          v12 = -1;
          do
            ++v12;
          while ( *(_WORD *)(*(_QWORD *)&pszSrc[12] + 2 * v12) );
          if ( (_DWORD)v12 && *(_WORD *)(*(_QWORD *)&pszSrc[12] + 2LL * (unsigned int)(v12 - 1)) != 92 )
            v11 = 1;
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v12 + v11 + 2));
          if ( Heap )
          {
            v13 = StringCchCopyNExW(
                    (STRSAFE_LPWSTR)Heap,
                    (unsigned int)(v12 + v11 + 2),
                    v10,
                    (unsigned int)v12,
                    &pszDest,
                    &cchDest,
                    v25);
            v14 = v13;
            if ( v13 >= 0 )
            {
              if ( !v11
                || (v15 = StringCchCopyNExW(pszDest, cchDest, L"\\", 1u, &pszDest, &cchDest, v25), v14 = v15, v15 >= 0) )
              {
                v16 = StringCchCopyNW(pszDest, cchDest, L"*", 1u);
                v14 = v16;
                if ( v16 >= 0 )
                {
                  v17 = (const WCHAR *)Heap;
                  NtCurrentTeb()->LastErrorValue = 0;
LABEL_33:
                  memset_0(&FindFileData, 0, sizeof(FindFileData));
                  FirstFileW = FindFirstFileW(v17, &FindFileData);
                  if ( FirstFileW != (HANDLE)-1LL )
                  {
                    while ( (FindFileData.dwFileAttributes & 0x10) != 0
                         && (CompareStringW(0x409u, 1u, FindFileData.cFileName, -1, L"System Volume Information", -1) == 2
                          || CompareStringW(0x409u, 1u, FindFileData.cFileName, -1, L"$Recycle.Bin", -1) == 2) )
                    {
                      memset_0(&FindFileData, 0, sizeof(FindFileData));
                      if ( !FindNextFileW(FirstFileW, &FindFileData) )
                        goto LABEL_40;
                    }
                    v6 = 1;
LABEL_40:
                    FindClose(FirstFileW);
                  }
                  goto LABEL_41;
                }
              }
            }
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
            NtCurrentTeb()->LastErrorValue = v14;
          }
          else
          {
            NtCurrentTeb()->LastErrorValue = 8;
          }
        }
        else
        {
          NtCurrentTeb()->LastErrorValue = 87;
        }
        v17 = 0;
        Heap = 0;
        LastError = GetLastError();
        v19 = LastError < 0;
        if ( LastError > 0 )
          v19 = 1;
        if ( !v19 )
          goto LABEL_41;
        v20 = GetLastError();
        v21 = v20 < 0;
        if ( v20 > 0 )
          v21 = 1;
        if ( v21 )
          goto LABEL_41;
        goto LABEL_33;
      }
LABEL_50:
      v3 = v34;
    }
  }
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v33 )
    ((void (__fastcall *)(struct IVdsDisk *))v33->lpVtbl->Release)(v33);
  if ( Disk >= 0 )
    *v3 = v6 == 0;
  return (unsigned int)Disk;
}

```

## disassembly

```asm
0x180041f90  mov     [rsp-8+arg_18], rbx
0x180041f95  push    rbp
0x180041f96  push    rsi
0x180041f97  push    rdi
0x180041f98  push    r12
0x180041f9a  push    r13
0x180041f9c  push    r14
0x180041f9e  push    r15
0x180041fa0  lea     rbp, [rsp-220h]
0x180041fa8  sub     rsp, 320h
0x180041faf  mov     rax, cs:__security_cookie
0x180041fb6  xor     rax, rsp
0x180041fb9  mov     [rbp+250h+var_40], rax
0x180041fc0  xor     r15d, r15d
0x180041fc3  mov     [rbp+250h+var_2D0], r8
0x180041fc7  xorps   xmm0, xmm0
0x180041fca  mov     [rsp+350h+var_2F8], r15
0x180041fcf  mov     rsi, r8
0x180041fd2  mov     [rsp+350h+var_2D8], r15
0x180041fd7  mov     ebx, edx
0x180041fd9  mov     [rsp+350h+var_2F0], r15
0x180041fde  mov     rdi, rcx
0x180041fe1  mov     [rsp+350h+var_300], r15
0x180041fe6  xor     eax, eax
0x180041fe8  mov     [rsp+350h+var_2E8], r15
0x180041fed  xor     edx, edx; Val
0x180041fef  mov     [rbp+250h+var_2C8], r15d
0x180041ff3  mov     r8d, 250h; Size
0x180041ff9  mov     [rbp+250h+var_294], eax
0x180041ffc  lea     rcx, [rbp+250h+FindFileData]; void *
0x180042000  mov     [rsp+350h+var_2E0], r15d
0x180042005  movups  [rbp+250h+var_2C4], xmm0
0x180042009  movups  [rbp+250h+var_2B4], xmm0
0x18004200d  movups  xmmword ptr [rbp+250h+pszSrc], xmm0
0x180042011  call    memset_0
0x180042016  test    rdi, rdi
0x180042019  jz      loc_180042457
0x18004201f  test    ebx, ebx
0x180042021  js      loc_180042457
0x180042027  test    rsi, rsi
0x18004202a  jz      loc_180042457
0x180042030  xor     r9d, r9d; struct IVdsAdvancedDisk **
0x180042033  mov     [rsp+350h+ppszDestEnd], r15; struct IVdsAdvancedDisk2 **
0x180042038  lea     r8, [rsp+350h+var_2D8]; struct IVdsDisk **
0x18004203d  mov     edx, ebx; int
0x18004203f  mov     rcx, rdi; struct IVdsService *
0x180042042  mov     r13d, r15d
0x180042045  call    ?GetDisk@@YAJPEAUIVdsService@@HPEAPEAUIVdsDisk@@PEAPEAUIVdsAdvancedDisk@@PEAPEAUIVdsAdvancedDisk2@@@Z; GetDisk(IVdsService *,int,IVdsDisk * *,IVdsAdvancedDisk * *,IVdsAdvancedDisk2 * *)
0x18004204a  mov     ebx, eax
0x18004204c  test    eax, eax
0x18004204e  js      loc_1800423F8
0x180042054  mov     rcx, [rsp+350h+var_2D8]
0x180042059  lea     rdx, [rsp+350h+var_2E8]
0x18004205e  mov     rax, [rcx]
0x180042061  mov     rax, [rax+20h]
0x180042065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004206a  mov     ebx, eax
0x18004206c  test    eax, eax
0x18004206e  js      loc_1800423F8
0x180042074  mov     rcx, [rsp+350h+var_2E8]
0x180042079  lea     rdx, [rsp+350h+var_2F0]
0x18004207e  mov     esi, r15d
0x180042081  mov     r12d, r15d
0x180042084  mov     rax, [rcx]
0x180042087  mov     rax, [rax+28h]
0x18004208b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042090  mov     ebx, eax
0x180042092  test    eax, eax
0x180042094  js      loc_1800423F4
0x18004209a  lea     edi, [r15+1]
0x18004209e  mov     rcx, [rsp+350h+var_2F0]
0x1800420a3  lea     r9, [rsp+350h+var_2E0]
0x1800420a8  lea     r8, [rsp+350h+var_2F8]
0x1800420ad  mov     edx, edi
0x1800420af  mov     rax, [rcx]
0x1800420b2  mov     rax, [rax+18h]
0x1800420b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800420bb  mov     ebx, eax
0x1800420bd  test    eax, eax
0x1800420bf  js      loc_1800423F4
0x1800420c5  cmp     eax, edi
0x1800420c7  jz      loc_1800423F4
0x1800420cd  test    r13d, r13d
0x1800420d0  jnz     loc_180042383
0x1800420d6  mov     rcx, [rsp+350h+var_2F8]
0x1800420db  lea     r8, [rsp+350h+var_300]
0x1800420e0  lea     rdx, IID_IVdsVolume
0x1800420e7  mov     rax, [rcx]
0x1800420ea  mov     rax, [rax]
0x1800420ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800420f2  test    eax, eax
0x1800420f4  js      loc_180042383
0x1800420fa  mov     rcx, [rsp+350h+var_300]
0x1800420ff  lea     rdx, [rbp+250h+var_2C8]
0x180042103  mov     rax, [rcx]
0x180042106  mov     rax, [rax+18h]
0x18004210a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004210f  test    eax, eax
0x180042111  js      loc_180042383
0x180042117  mov     r14, [rbp+250h+pszSrc+0Ch]
0x18004211b  mov     [rsp+350h+pszDest], r15
0x180042120  mov     [rsp+350h+cchDest], r15
0x180042125  test    r14, r14
0x180042128  jz      loc_180042267
0x18004212e  mov     edi, r15d
0x180042131  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180042135  inc     rbx
0x180042138  cmp     [r14+rbx*2], r15w
0x18004213d  jnz     short loc_180042135
0x18004213f  test    ebx, ebx
0x180042141  jz      short loc_180042158
0x180042143  mov     eax, 5Ch ; '\'
0x180042148  lea     ecx, [rbx-1]
0x18004214b  cmp     ax, [r14+rcx*2]
0x180042150  mov     eax, 1
0x180042155  cmovnz  edi, eax
0x180042158  mov     rcx, gs:60h
0x180042161  lea     eax, [rdi+2]
0x180042164  add     eax, ebx
0x180042166  mov     edx, 8; Flags
0x18004216b  mov     r15d, eax
0x18004216e  mov     rcx, [rcx+30h]; HeapHandle
0x180042172  lea     r8, [rax+rax]; Size
0x180042176  call    cs:__imp_RtlAllocateHeap
0x18004217c  mov     rsi, rax
0x18004217f  test    rax, rax
0x180042182  jnz     short loc_18004219F
0x180042184  mov     rax, gs:30h
0x18004218d  lea     edi, [rsi+1]
0x180042190  xor     r15d, r15d
0x180042193  mov     dword ptr [rax+68h], 8
0x18004219a  jmp     loc_180042277
0x18004219f  lea     rax, [rsp+350h+cchDest]
0x1800421a4  mov     r9d, ebx; cchToCopy
0x1800421a7  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x1800421ac  mov     r8, r14; pszSrc
0x1800421af  lea     rax, [rsp+350h+pszDest]
0x1800421b4  mov     rdx, r15; cchDest
0x1800421b7  mov     rcx, rsi; pszDest
0x1800421ba  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x1800421bf  call    StringCchCopyNExW
0x1800421c4  xor     r15d, r15d
0x1800421c7  mov     ebx, eax
0x1800421c9  test    eax, eax
0x1800421cb  js      short loc_180042239
0x1800421cd  test    edi, edi
0x1800421cf  lea     edi, [r15+1]
0x1800421d3  jz      short loc_180042208
0x1800421d5  mov     rdx, [rsp+350h+cchDest]; cchDest
0x1800421da  lea     rax, [rsp+350h+cchDest]
0x1800421df  mov     rcx, [rsp+350h+pszDest]; pszDest
0x1800421e4  lea     r8, asc_180084C70; "\\"
0x1800421eb  mov     [rsp+350h+pcchRemaining], rax; pcchRemaining
0x1800421f0  mov     r9d, edi; cchToCopy
0x1800421f3  lea     rax, [rsp+350h+pszDest]
0x1800421f8  mov     [rsp+350h+ppszDestEnd], rax; ppszDestEnd
0x1800421fd  call    StringCchCopyNExW
0x180042202  mov     ebx, eax
0x180042204  test    eax, eax
0x180042206  js      short loc_18004223E
0x180042208  mov     rdx, [rsp+350h+cchDest]; cchDest
0x18004220d  lea     r8, asc_1800850E8; "*"
0x180042214  mov     rcx, [rsp+350h+pszDest]; pszDest
0x180042219  mov     r9, rdi; cchToCopy
0x18004221c  call    StringCchCopyNW
0x180042221  mov     ebx, eax
0x180042223  test    eax, eax
0x180042225  js      short loc_18004223E
0x180042227  mov     rax, gs:30h
0x180042230  mov     rbx, rsi
0x180042233  mov     [rax+68h], r15d
0x180042237  jmp     short loc_1800422B1
0x180042239  mov     edi, 1
0x18004223e  mov     rcx, gs:60h
0x180042247  mov     r8, rsi; P
0x18004224a  xor     edx, edx; Flags
0x18004224c  mov     rcx, [rcx+30h]; HeapHandle
0x180042250  call    cs:__imp_RtlFreeHeap
0x180042256  mov     rax, gs:30h
0x18004225f  movzx   ecx, bx
0x180042262  mov     [rax+68h], ecx
0x180042265  jmp     short loc_180042277
0x180042267  mov     rax, gs:30h
0x180042270  mov     dword ptr [rax+68h], 57h ; 'W'
0x180042277  mov     rbx, r15
0x18004227a  mov     rsi, r15
0x18004227d  call    cs:__imp_GetLastError
0x180042283  test    eax, eax
0x180042285  jle     short loc_180042291
0x180042287  movzx   eax, ax
0x18004228a  or      eax, 80070000h
0x18004228f  test    eax, eax
0x180042291  jns     loc_180042383
0x180042297  call    cs:__imp_GetLastError
0x18004229d  test    eax, eax
0x18004229f  jle     short loc_1800422AB
0x1800422a1  movzx   eax, ax
0x1800422a4  or      eax, 80070000h
0x1800422a9  test    eax, eax
0x1800422ab  js      loc_180042383
0x1800422b1  xor     edx, edx; Val
0x1800422b3  lea     rcx, [rbp+250h+FindFileData]; void *
0x1800422b7  mov     r8d, 250h; Size
0x1800422bd  call    memset_0
0x1800422c2  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x1800422c6  mov     rcx, rbx; lpFileName
0x1800422c9  call    cs:__imp_FindFirstFileW
0x1800422cf  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800422d3  mov     rbx, rax
0x1800422d6  cmp     rax, r14
0x1800422d9  jnz     short loc_1800422E4
0x1800422db  test    r12d, r12d
0x1800422de  jz      loc_180042383
0x1800422e4  test    byte ptr [rbp+250h+FindFileData.dwFileAttributes], 10h
0x1800422e8  jz      loc_18004236F
0x1800422ee  lea     rax, aSystemVolumeIn; "System Volume Information"
0x1800422f5  mov     dword ptr [rsp+350h+pcchRemaining], r14d; cchCount2
0x1800422fa  mov     r12d, 409h
0x180042300  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x180042305  mov     ecx, r12d; Locale
0x180042308  lea     r8, [rbp+250h+FindFileData.cFileName]; lpString1
0x18004230c  mov     r9d, r14d; cchCount1
0x18004230f  mov     edx, edi; dwCmpFlags
0x180042311  call    cs:__imp_CompareStringW
0x180042317  cmp     eax, 2
0x18004231a  jz      short loc_180042344
0x18004231c  lea     rax, aRecycleBin; "$Recycle.Bin"
0x180042323  mov     dword ptr [rsp+350h+pcchRemaining], r14d; cchCount2
0x180042328  mov     r9d, r14d; cchCount1
0x18004232b  mov     [rsp+350h+ppszDestEnd], rax; lpString2
0x180042330  lea     r8, [rbp+250h+FindFileData.cFileName]; lpString1
0x180042334  mov     edx, edi; dwCmpFlags
0x180042336  mov     ecx, r12d; Locale
0x180042339  call    cs:__imp_CompareStringW
0x18004233f  cmp     eax, 2
0x180042342  jnz     short loc_18004236F
0x180042344  xor     edx, edx; Val
0x180042346  lea     rcx, [rbp+250h+FindFileData]; void *
0x18004234a  mov     r8d, 250h; Size
0x180042350  call    memset_0
0x180042355  lea     rdx, [rbp+250h+FindFileData]; lpFindFileData
0x180042359  mov     rcx, rbx; hFindFile
0x18004235c  call    cs:__imp_FindNextFileW
0x180042362  mov     r12d, eax
0x180042365  test    eax, eax
0x180042367  jnz     loc_1800422E4
0x18004236d  jmp     short loc_180042375
0x18004236f  mov     r13d, edi
0x180042372  mov     r12d, r15d
0x180042375  cmp     rbx, r14
0x180042378  jz      short loc_180042383
0x18004237a  mov     rcx, rbx; hFindFile
0x18004237d  call    cs:__imp_FindClose
0x180042383  mov     rcx, [rbp+250h+pszSrc+0Ch]; pv
0x180042387  test    rcx, rcx
0x18004238a  jz      short loc_180042396
0x18004238c  call    cs:__imp_CoTaskMemFree
0x180042392  mov     [rbp+250h+pszSrc+0Ch], r15
0x180042396  test    rsi, rsi
0x180042399  jz      short loc_1800423B5
0x18004239b  call    cs:__imp_GetProcessHeap
0x1800423a1  mov     r8, rsi; lpMem
0x1800423a4  xor     edx, edx; dwFlags
0x1800423a6  mov     rcx, rax; hHeap
0x1800423a9  call    cs:__imp_HeapFree
0x1800423af  test    eax, eax
0x1800423b1  cmovnz  rsi, r15
0x1800423b5  mov     rcx, [rsp+350h+var_300]
0x1800423ba  test    rcx, rcx
0x1800423bd  jz      short loc_1800423D0
0x1800423bf  mov     rax, [rcx]
0x1800423c2  mov     rax, [rax+10h]
0x1800423c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423cb  mov     [rsp+350h+var_300], r15
0x1800423d0  mov     rcx, [rsp+350h+var_2F8]
0x1800423d5  test    rcx, rcx
0x1800423d8  jz      loc_18004209E
0x1800423de  mov     rax, [rcx]
0x1800423e1  mov     rax, [rax+10h]
0x1800423e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423ea  mov     [rsp+350h+var_2F8], r15
0x1800423ef  jmp     loc_18004209E
0x1800423f4  mov     rsi, [rbp+250h+var_2D0]
0x1800423f8  mov     rcx, [rsp+350h+var_2F0]
0x1800423fd  test    rcx, rcx
0x180042400  jz      short loc_180042413
0x180042402  mov     rax, [rcx]
0x180042405  mov     rax, [rax+10h]
0x180042409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004240e  mov     [rsp+350h+var_2F0], r15
0x180042413  mov     rcx, [rsp+350h+var_2E8]
0x180042418  test    rcx, rcx
0x18004241b  jz      short loc_18004242E
0x18004241d  mov     rax, [rcx]
0x180042420  mov     rax, [rax+10h]
0x180042424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042429  mov     [rsp+350h+var_2E8], r15
0x18004242e  mov     rcx, [rsp+350h+var_2D8]
0x180042433  test    rcx, rcx
0x180042436  jz      short loc_180042444
  ... truncated ...
```
