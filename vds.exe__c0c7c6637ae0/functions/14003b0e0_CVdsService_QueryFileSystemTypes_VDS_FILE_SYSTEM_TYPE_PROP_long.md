# CVdsService::QueryFileSystemTypes(_VDS_FILE_SYSTEM_TYPE_PROP * *,long *)

- ea: `0x14003b0e0`
- end: `0x14003b331`
- name: `?QueryFileSystemTypes@CVdsService@@UEAAJPEAPEAU_VDS_FILE_SYSTEM_TYPE_PROP@@PEAJ@Z`
- size: `593`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, struct _VDS_FILE_SYSTEM_TYPE_PROP **, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006e60`
- `0x14003b0e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003b12c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003b14a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003b1ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003b12c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003b14a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003b1ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003b1cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003b1e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003b1f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003b1cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003b1e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003b1f7`
- `vdsutil!VdsHeapFree` at `0x14003b1dd`
- `vdsutil!VdsHeapFree` at `0x14003b1f1`
- `vdsutil!VdsHeapFree` at `0x14003b205`
- `vdsutil!VdsHeapFree` at `0x14003b1dd`
- `vdsutil!VdsHeapFree` at `0x14003b1f1`
- `vdsutil!VdsHeapFree` at `0x14003b205`
- `vdsutil!VdsTraceEx` at `0x14003b1c4`
- `vdsutil!VdsTraceEx` at `0x14003b30b`
- `vdsutil!VdsTraceEx` at `0x14003b1c4`
- `vdsutil!VdsTraceEx` at `0x14003b30b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003b108`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003b108`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003b2f6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003b317`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003b2f6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003b317`

## string_xrefs

- `0x14003b0f5`: `CVdsService::QueryFileSystemTypes()`
- `0x14003b300`: `CVdsService::QueryFileSystemTypes, 1`
- `0x14003b13c`: `CVdsService::QueryFileSystemTypes, 2`
- `0x14003b158`: `CVdsService::QueryFileSystemTypes, 3`
- `0x14003b1b9`: `CVdsService::QueryFileSystemTypes, 4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsService::QueryFileSystemTypes(
        CVdsService *this,
        struct _VDS_FILE_SYSTEM_TYPE_PROP **a2,
        int *a3)
{
  char *v5; // rbx
  unsigned __int16 *v6; // rsi
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rax
  unsigned int v9; // edi
  HANDLE ProcessHeap; // rax
  HANDLE v11; // rax
  HANDLE v12; // rax
  __int64 v13; // r10
  int v14; // r10d
  _BYTE v16[72]; // [rsp+20h] [rbp-48h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v16, 0x5Eu, "CVdsService::QueryFileSystemTypes()");
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v5 = (char *)CoTaskMemAlloc(0xC8u);
    if ( v5 )
    {
      v7 = (unsigned __int16 *)CoTaskMemAlloc(0x22u);
      v6 = v7;
      if ( v7 )
      {
        StringCchCopyW(v7, 0x11u, L":*+=|\\;.,<>?/[]\"");
        *(_DWORD *)v5 = 2;
        StringCchCopyW((unsigned __int16 *)v5 + 2, 8u, L"FAT");
        *(_QWORD *)(v5 + 20) = 67043371;
        *((_DWORD *)v5 + 7) = 11;
        *((_QWORD *)v5 + 4) = v6;
        v8 = (unsigned __int16 *)CoTaskMemAlloc(0x22u);
        if ( v8 )
        {
          v9 = 0;
          StringCchCopyW(v8, 0x11u, L":*+=|\\;.,<>?/[]\"");
          *((_DWORD *)v5 + 10) = 3;
          StringCchCopyW((unsigned __int16 *)v5 + 22, 8u, L"FAT32");
          *(_QWORD *)(v5 + 60) = 67043371;
          *((_DWORD *)v5 + 17) = 11;
          *((_QWORD *)v5 + 9) = v13;
          *((_DWORD *)v5 + 20) = 4;
          StringCchCopyW((unsigned __int16 *)v5 + 42, 8u, L"NTFS");
          *((_DWORD *)v5 + 25) = 16711807;
          *((_DWORD *)v5 + 26) = 983040;
          *((_DWORD *)v5 + 27) = 32;
          *((_QWORD *)v5 + 14) = 0;
          *((_DWORD *)v5 + 30) = 5;
          StringCchCopyW((unsigned __int16 *)v5 + 62, 8u, L"CDFS");
          *(_QWORD *)(v5 + 140) = 0;
          *((_DWORD *)v5 + 37) = 0;
          *((_QWORD *)v5 + 19) = 0;
          *((_DWORD *)v5 + 40) = 6;
          StringCchCopyW((unsigned __int16 *)v5 + 82, 8u, L"UDF");
          *(_QWORD *)(v5 + 180) = 0;
          *((_DWORD *)v5 + 47) = 0;
          *((_QWORD *)v5 + 24) = 0;
          *a3 = v14;
          *a2 = (struct _VDS_FILE_SYSTEM_TYPE_PROP *)v5;
          goto LABEL_11;
        }
        VdsTraceEx(94, 0, "CVdsService::QueryFileSystemTypes, 4");
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsService::QueryFileSystemTypes, 3");
      }
    }
    else
    {
      v6 = 0;
      VdsTraceEx(94, 0, "CVdsService::QueryFileSystemTypes, 2");
    }
    v9 = -2147024882;
    ProcessHeap = GetProcessHeap();
    VdsHeapFree(ProcessHeap, 0, v5);
    v11 = GetProcessHeap();
    VdsHeapFree(v11, 0, v6);
    v12 = GetProcessHeap();
    VdsHeapFree(v12, 0, 0);
LABEL_11:
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
    return v9;
  }
  VdsTraceEx(94, 0, "CVdsService::QueryFileSystemTypes, 1");
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
  return 2147942487LL;
}

```

## disassembly

```asm
0x14003b0e0  push    rbx
0x14003b0e2  push    rbp
0x14003b0e3  push    rsi
0x14003b0e4  push    rdi
0x14003b0e5  push    r13
0x14003b0e7  push    r14
0x14003b0e9  push    r15
0x14003b0eb  sub     rsp, 30h
0x14003b0ef  mov     r14, r8
0x14003b0f2  mov     r15, rdx
0x14003b0f5  lea     r8, aCvdsserviceQue_14; "CVdsService::QueryFileSystemTypes()"
0x14003b0fc  mov     edi, 5Eh ; '^'
0x14003b101  mov     edx, edi
0x14003b103  lea     rcx, [rsp+68h+var_48]
0x14003b108  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003b10e  nop
0x14003b10f  xor     ebp, ebp
0x14003b111  test    r15, r15
0x14003b114  jz      loc_14003B300
0x14003b11a  test    r14, r14
0x14003b11d  jz      loc_14003B300
0x14003b123  mov     [r15], rbp
0x14003b126  mov     [r14], ebp
0x14003b129  lea     ecx, [rdi+6Ah]; cb
0x14003b12c  call    cs:__imp_CoTaskMemAlloc
0x14003b132  mov     rbx, rax
0x14003b135  test    rax, rax
0x14003b138  jnz     short loc_14003B145
0x14003b13a  mov     esi, ebp
0x14003b13c  lea     r8, aCvdsserviceQue_3; "CVdsService::QueryFileSystemTypes, 2"
0x14003b143  jmp     short loc_14003B1C0
0x14003b145  mov     ecx, 22h ; '"'; cb
0x14003b14a  call    cs:__imp_CoTaskMemAlloc
0x14003b150  mov     rsi, rax
0x14003b153  test    rax, rax
0x14003b156  jnz     short loc_14003B161
0x14003b158  lea     r8, aCvdsserviceQue_5; "CVdsService::QueryFileSystemTypes, 3"
0x14003b15f  jmp     short loc_14003B1C0
0x14003b161  lea     r8, asc_14006CEC0; ":*+=|\\;.,<>?/[]\""
0x14003b168  mov     edx, 11h; unsigned __int64
0x14003b16d  mov     rcx, rsi; unsigned __int16 *
0x14003b170  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003b175  mov     dword ptr [rbx], 2
0x14003b17b  lea     rcx, [rbx+4]; unsigned __int16 *
0x14003b17f  lea     r8, aFat; "FAT"
0x14003b186  mov     r13d, 8
0x14003b18c  mov     edx, r13d; unsigned __int64
0x14003b18f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003b194  mov     qword ptr [rbx+14h], 3FF002Bh
0x14003b19c  mov     dword ptr [rbx+1Ch], 0Bh
0x14003b1a3  mov     [rbx+20h], rsi
0x14003b1a7  lea     ecx, [r13+1Ah]; cb
0x14003b1ab  call    cs:__imp_CoTaskMemAlloc
0x14003b1b1  mov     r10, rax
0x14003b1b4  test    rax, rax
0x14003b1b7  jnz     short loc_14003B210
0x14003b1b9  lea     r8, aCvdsserviceQue_13; "CVdsService::QueryFileSystemTypes, 4"
0x14003b1c0  xor     edx, edx
0x14003b1c2  mov     ecx, edi
0x14003b1c4  call    cs:__imp_VdsTraceEx
0x14003b1ca  mov     edi, 8007000Eh
0x14003b1cf  call    cs:__imp_GetProcessHeap
0x14003b1d5  mov     rcx, rax
0x14003b1d8  mov     r8, rbx
0x14003b1db  xor     edx, edx
0x14003b1dd  call    cs:__imp_VdsHeapFree
0x14003b1e3  call    cs:__imp_GetProcessHeap
0x14003b1e9  mov     rcx, rax
0x14003b1ec  mov     r8, rsi
0x14003b1ef  xor     edx, edx
0x14003b1f1  call    cs:__imp_VdsHeapFree
0x14003b1f7  call    cs:__imp_GetProcessHeap
0x14003b1fd  mov     rcx, rax
0x14003b200  xor     r8d, r8d
0x14003b203  xor     edx, edx
0x14003b205  call    cs:__imp_VdsHeapFree
0x14003b20b  jmp     loc_14003B2F1
0x14003b210  mov     edi, ebp
0x14003b212  lea     r8, asc_14006CE98; ":*+=|\\;.,<>?/[]\""
0x14003b219  mov     edx, 11h; unsigned __int64
0x14003b21e  mov     rcx, r10; unsigned __int16 *
0x14003b221  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003b226  mov     dword ptr [rbx+28h], 3
0x14003b22d  lea     rcx, [rbx+2Ch]; unsigned __int16 *
0x14003b231  lea     r8, aFat32; "FAT32"
0x14003b238  mov     rdx, r13; unsigned __int64
0x14003b23b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003b240  mov     qword ptr [rbx+3Ch], 3FF002Bh
0x14003b248  mov     dword ptr [rbx+44h], 0Bh
0x14003b24f  mov     [rbx+48h], r10
0x14003b253  mov     dword ptr [rbx+50h], 4
0x14003b25a  lea     rcx, [rbx+54h]; unsigned __int16 *
0x14003b25e  lea     r8, aNtfs; "NTFS"
0x14003b265  mov     rdx, r13; unsigned __int64
0x14003b268  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003b26d  mov     dword ptr [rbx+64h], 0FF007Fh
0x14003b274  mov     dword ptr [rbx+68h], 0F0000h
0x14003b27b  mov     dword ptr [rbx+6Ch], 20h ; ' '
0x14003b282  mov     [rbx+70h], rbp
0x14003b286  mov     r10d, 5
0x14003b28c  mov     [rbx+78h], r10d
0x14003b290  lea     rcx, [rbx+7Ch]; unsigned __int16 *
0x14003b294  lea     r8, aCdfs; "CDFS"
0x14003b29b  mov     rdx, r13; unsigned __int64
0x14003b29e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003b2a3  mov     [rbx+8Ch], rbp
0x14003b2aa  mov     [rbx+94h], ebp
0x14003b2b0  mov     [rbx+98h], rbp
0x14003b2b7  mov     dword ptr [rbx+0A0h], 6
0x14003b2c1  lea     rcx, [rbx+0A4h]; unsigned __int16 *
0x14003b2c8  lea     r8, aUdf; "UDF"
0x14003b2cf  mov     rdx, r13; unsigned __int64
0x14003b2d2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003b2d7  mov     [rbx+0B4h], rbp
0x14003b2de  mov     [rbx+0BCh], ebp
0x14003b2e4  mov     [rbx+0C0h], rbp
0x14003b2eb  mov     [r14], r10d
0x14003b2ee  mov     [r15], rbx
0x14003b2f1  lea     rcx, [rsp+68h+var_48]
0x14003b2f6  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003b2fc  mov     eax, edi
0x14003b2fe  jmp     short loc_14003B322
0x14003b300  lea     r8, aCvdsserviceQue_8; "CVdsService::QueryFileSystemTypes, 1"
0x14003b307  xor     edx, edx
0x14003b309  mov     ecx, edi
0x14003b30b  call    cs:__imp_VdsTraceEx
0x14003b311  nop
0x14003b312  lea     rcx, [rsp+68h+var_48]
0x14003b317  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003b31d  mov     eax, 80070057h
0x14003b322  add     rsp, 30h
0x14003b326  pop     r15
0x14003b328  pop     r14
0x14003b32a  pop     r13
0x14003b32c  pop     rdi
0x14003b32d  pop     rsi
0x14003b32e  pop     rbp
0x14003b32f  pop     rbx
0x14003b330  retn
```
