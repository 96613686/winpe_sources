# CVdsVolume::GetFileSystemTypeName(ushort * *)

- ea: `0x140042230`
- end: `0x1400424dc`
- name: `?GetFileSystemTypeName@CVdsVolume@@UEAAJPEAPEAG@Z`
- size: `684`
- prototype: `int(CVdsVolume *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140009990`
- `0x140042230`
- `0x1400424e4`
- `0x1400514b8`
- `0x140052e80`

## import_xrefs

- `msvcrt!wcsstr` at `0x1400422f6`
- `msvcrt!wcsstr` at `0x1400422f6`
- `msvcrt!wcscpy_s` at `0x140042384`
- `msvcrt!wcscpy_s` at `0x140042409`
- `msvcrt!wcscpy_s` at `0x14004245a`
- `msvcrt!wcscpy_s` at `0x140042384`
- `msvcrt!wcscpy_s` at `0x140042409`
- `msvcrt!wcscpy_s` at `0x14004245a`
- `msvcrt!_wcsnicmp` at `0x140042342`
- `msvcrt!_wcsnicmp` at `0x140042342`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14004236c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400423eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140042442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14004236c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400423eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140042442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004235e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400423c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140042434`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400424a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004235e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400423c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140042434`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400424a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140042469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140042469`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004248f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004248f`
- `vdsutil!GetFileSystemRecognitionName` at `0x140042397`
- `vdsutil!GetFileSystemRecognitionName` at `0x140042397`
- `vdsutil!VdsHeapFree` at `0x140042477`
- `vdsutil!VdsHeapFree` at `0x140042477`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140042293`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140042293`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400424b0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400424b0`
- `vdsutil!VdsTraceW` at `0x1400422c0`
- `vdsutil!VdsTraceW` at `0x140042320`
- `vdsutil!VdsTraceW` at `0x1400423b7`
- `vdsutil!VdsTraceW` at `0x140042426`
- `vdsutil!VdsTraceW` at `0x1400422c0`
- `vdsutil!VdsTraceW` at `0x140042320`
- `vdsutil!VdsTraceW` at `0x1400423b7`
- `vdsutil!VdsTraceW` at `0x140042426`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsVolume::GetFileSystemTypeName(CVdsVolume *this, unsigned __int16 **a2)
{
  __int64 v4; // rdx
  int v5; // eax
  int FileSystemRecognitionName; // edi
  int FileSystemTypeNameInternal; // eax
  int v8; // eax
  unsigned __int16 *v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rcx
  unsigned __int16 *v12; // rax
  unsigned int v13; // eax
  unsigned __int16 *v14; // rax
  wchar_t *v15; // rbx
  HANDLE ProcessHeap; // rax
  _BYTE v18[8]; // [rsp+20h] [rbp-29h] BYREF
  wchar_t *Source; // [rsp+28h] [rbp-21h] BYREF
  HANDLE hObject; // [rsp+30h] [rbp-19h] BYREF
  _BYTE v21[16]; // [rsp+38h] [rbp-11h] BYREF
  struct _VDS_VOLUME_PROP v22; // [rsp+48h] [rbp-1h] BYREF

  hObject = 0;
  memset(&v22, 0, sizeof(v22));
  v18[0] = 0;
  Source = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v21, 0x5Eu, "CVdsVolume::GetFileSystemTypeName()");
  *a2 = 0;
  v5 = CVdsVolume::OpenHandle((CVdsVolume *)((char *)this - 32), v4, &hObject, &v22);
  FileSystemRecognitionName = v5;
  if ( v5 >= 0 )
  {
    FileSystemTypeNameInternal = CVdsVolume::GetFileSystemTypeNameInternal(hObject, a2);
    FileSystemRecognitionName = FileSystemTypeNameInternal;
    if ( FileSystemTypeNameInternal >= 0 )
    {
      if ( v22.pwszName )
      {
        if ( !wcsstr(v22.pwszName, L"CdRom") )
        {
          v8 = FveDetectVolume(v22.pwszName, v18);
          FileSystemRecognitionName = v8;
          if ( v8 < 0 )
          {
            VdsTraceW(0, L"CVdsVolume::GetFileSystemTypeName, 3, hr=%lX", (unsigned int)v8);
            FileSystemRecognitionName = 0;
          }
        }
      }
      if ( *a2 && !_wcsnicmp(*a2, L"RAW", 3u) )
      {
        if ( v18[0] )
        {
          if ( *a2 )
          {
            CoTaskMemFree(*a2);
            *a2 = 0;
          }
          v9 = (unsigned __int16 *)CoTaskMemAlloc(0x10u);
          *a2 = v9;
          wcscpy_s(v9, 8u, L"Unknown");
        }
        else
        {
          FileSystemRecognitionName = GetFileSystemRecognitionName(hObject, &Source);
          if ( FileSystemRecognitionName < 0 )
          {
            FileSystemRecognitionName = 0;
          }
          else
          {
            VdsTraceW(2, L"CVdsVolume::GetFileSystemTypeName, 3b, file system name=%s", Source);
            if ( *a2 )
            {
              CoTaskMemFree(*a2);
              *a2 = 0;
            }
            v10 = -1;
            v11 = -1;
            do
              ++v11;
            while ( Source[v11] );
            v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * v11 + 2);
            *a2 = v12;
            do
              ++v10;
            while ( Source[v10] );
            v13 = wcscpy_s(v12, v10 + 1, Source);
            if ( v13 )
            {
              VdsTraceW(2, L"CVdsVolume::GetFileSystemTypeName, 3c, file system name=%s, err=%ld", Source, v13);
              if ( *a2 )
              {
                CoTaskMemFree(*a2);
                *a2 = 0;
              }
              v14 = (unsigned __int16 *)CoTaskMemAlloc(8u);
              *a2 = v14;
              wcscpy_s(v14, 4u, L"RAW");
            }
          }
          v15 = Source;
          ProcessHeap = GetProcessHeap();
          VdsHeapFree(ProcessHeap, 0, v15);
          Source = 0;
        }
      }
    }
    else
    {
      VdsTraceW(0, L"CVdsVolume::GetFileSystemTypeName, 2, hr=%lX", (unsigned int)FileSystemTypeNameInternal);
    }
  }
  else
  {
    VdsTraceW(0, L"CVdsVolume::GetFileSystemTypeName, 1, hr=%lX", (unsigned int)v5);
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v22.pwszName )
  {
    CoTaskMemFree(v22.pwszName);
    v22.pwszName = 0;
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v21);
  return (unsigned int)FileSystemRecognitionName;
}

```

## disassembly

```asm
0x140042230  mov     [rsp-8+arg_10], rbx
0x140042235  mov     [rsp-8+arg_18], rsi
0x14004223a  push    rbp
0x14004223b  push    rdi
0x14004223c  push    r14
0x14004223e  lea     rbp, [rsp-47h]
0x140042243  sub     rsp, 90h
0x14004224a  mov     rax, cs:__security_cookie
0x140042251  xor     rax, rsp
0x140042254  mov     [rbp+57h+var_20], rax
0x140042258  mov     rsi, rdx
0x14004225b  mov     rbx, rcx
0x14004225e  xor     r14d, r14d
0x140042261  mov     [rbp+57h+hObject], r14
0x140042265  mov     [rbp+57h+var_58.id.Data1], r14d
0x140042269  xorps   xmm0, xmm0
0x14004226c  xor     eax, eax
0x14004226e  movups  xmmword ptr [rbp+57h+var_58.id.Data2], xmm0
0x140042272  movups  xmmword ptr [rbp+57h+var_58.status], xmm0
0x140042276  movups  xmmword ptr [rbp+57h+var_58.ullSize+4], xmm0
0x14004227a  mov     dword ptr [rbp+57h+var_58.pwszName+4], eax
0x14004227d  mov     [rbp+57h+var_80], r14b
0x140042281  mov     [rbp+57h+Source], r14
0x140042285  lea     r8, aCvdsvolumeGetf_1; "CVdsVolume::GetFileSystemTypeName()"
0x14004228c  lea     edx, [rax+5Eh]
0x14004228f  lea     rcx, [rbp+57h+var_68]
0x140042293  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140042299  nop
0x14004229a  mov     [rsi], r14
0x14004229d  lea     rcx, [rbx-20h]; this
0x1400422a1  lea     r9, [rbp+57h+var_58]; struct _VDS_VOLUME_PROP *
0x1400422a5  lea     r8, [rbp+57h+hObject]; void **
0x1400422a9  call    ?OpenHandle@CVdsVolume@@QEAAJKPEAPEAXPEAU_VDS_VOLUME_PROP@@@Z; CVdsVolume::OpenHandle(ulong,void * *,_VDS_VOLUME_PROP *)
0x1400422ae  mov     edi, eax
0x1400422b0  test    eax, eax
0x1400422b2  jns     short loc_1400422CB
0x1400422b4  lea     rdx, aCvdsvolumeGetf_2; "CVdsVolume::GetFileSystemTypeName, 1, h"...
0x1400422bb  mov     r8d, eax
0x1400422be  xor     ecx, ecx
0x1400422c0  call    cs:__imp_VdsTraceW
0x1400422c6  jmp     loc_140042481
0x1400422cb  mov     rdx, rsi; unsigned __int16 **
0x1400422ce  mov     rcx, [rbp+57h+hObject]; FileHandle
0x1400422d2  call    ?GetFileSystemTypeNameInternal@CVdsVolume@@SAJPEAXPEAPEAG@Z; CVdsVolume::GetFileSystemTypeNameInternal(void *,ushort * *)
0x1400422d7  mov     edi, eax
0x1400422d9  test    eax, eax
0x1400422db  jns     short loc_1400422E6
0x1400422dd  lea     rdx, aCvdsvolumeGetf_7; "CVdsVolume::GetFileSystemTypeName, 2, h"...
0x1400422e4  jmp     short loc_1400422BB
0x1400422e6  mov     rcx, [rbp+57h+var_58.pwszName]; Str
0x1400422ea  test    rcx, rcx
0x1400422ed  jz      short loc_140042329
0x1400422ef  lea     rdx, aCdrom; "CdRom"
0x1400422f6  call    cs:__imp_wcsstr
0x1400422fc  test    rax, rax
0x1400422ff  jnz     short loc_140042329
0x140042301  lea     rdx, [rbp+57h+var_80]
0x140042305  mov     rcx, [rbp+57h+var_58.pwszName]
0x140042309  call    FveDetectVolume
0x14004230e  mov     edi, eax
0x140042310  test    eax, eax
0x140042312  jns     short loc_140042329
0x140042314  mov     r8d, eax
0x140042317  lea     rdx, aCvdsvolumeGetf_3; "CVdsVolume::GetFileSystemTypeName, 3, h"...
0x14004231e  xor     ecx, ecx
0x140042320  call    cs:__imp_VdsTraceW
0x140042326  mov     edi, r14d
0x140042329  mov     rcx, [rsi]; String1
0x14004232c  test    rcx, rcx
0x14004232f  jz      loc_140042481
0x140042335  mov     r8d, 3; MaxCount
0x14004233b  lea     rdx, aRaw; "RAW"
0x140042342  call    cs:__imp__wcsnicmp
0x140042348  test    eax, eax
0x14004234a  jnz     loc_140042481
0x140042350  cmp     [rbp+57h+var_80], r14b
0x140042354  jz      short loc_14004238F
0x140042356  mov     rcx, [rsi]; pv
0x140042359  test    rcx, rcx
0x14004235c  jz      short loc_140042367
0x14004235e  call    cs:__imp_CoTaskMemFree
0x140042364  mov     [rsi], r14
0x140042367  mov     ecx, 10h; cb
0x14004236c  call    cs:__imp_CoTaskMemAlloc
0x140042372  mov     [rsi], rax
0x140042375  lea     r8, aUnknown; "Unknown"
0x14004237c  mov     edx, 8; SizeInWords
0x140042381  mov     rcx, rax; Destination
0x140042384  call    cs:__imp_wcscpy_s
0x14004238a  jmp     loc_140042481
0x14004238f  lea     rdx, [rbp+57h+Source]
0x140042393  mov     rcx, [rbp+57h+hObject]
0x140042397  call    cs:__imp_GetFileSystemRecognitionName
0x14004239d  mov     edi, eax
0x14004239f  test    eax, eax
0x1400423a1  js      loc_140042462
0x1400423a7  mov     r8, [rbp+57h+Source]
0x1400423ab  lea     rdx, aCvdsvolumeGetf_28; "CVdsVolume::GetFileSystemTypeName, 3b, "...
0x1400423b2  mov     ecx, 2
0x1400423b7  call    cs:__imp_VdsTraceW
0x1400423bd  mov     rcx, [rsi]; pv
0x1400423c0  test    rcx, rcx
0x1400423c3  jz      short loc_1400423CE
0x1400423c5  call    cs:__imp_CoTaskMemFree
0x1400423cb  mov     [rsi], r14
0x1400423ce  mov     rax, [rbp+57h+Source]
0x1400423d2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400423d6  mov     rcx, rbx
0x1400423d9  inc     rcx
0x1400423dc  cmp     [rax+rcx*2], r14w
0x1400423e1  jnz     short loc_1400423D9
0x1400423e3  lea     rcx, ds:2[rcx*2]; cb
0x1400423eb  call    cs:__imp_CoTaskMemAlloc
0x1400423f1  mov     [rsi], rax
0x1400423f4  mov     r8, [rbp+57h+Source]; Source
0x1400423f8  inc     rbx
0x1400423fb  cmp     [r8+rbx*2], r14w
0x140042400  jnz     short loc_1400423F8
0x140042402  lea     rdx, [rbx+1]; SizeInWords
0x140042406  mov     rcx, rax; Destination
0x140042409  call    cs:__imp_wcscpy_s
0x14004240f  test    eax, eax
0x140042411  jz      short loc_140042465
0x140042413  mov     r9d, eax
0x140042416  mov     r8, [rbp+57h+Source]
0x14004241a  lea     rdx, aCvdsvolumeGetf_22; "CVdsVolume::GetFileSystemTypeName, 3c, "...
0x140042421  mov     ecx, 2
0x140042426  call    cs:__imp_VdsTraceW
0x14004242c  mov     rcx, [rsi]; pv
0x14004242f  test    rcx, rcx
0x140042432  jz      short loc_14004243D
0x140042434  call    cs:__imp_CoTaskMemFree
0x14004243a  mov     [rsi], r14
0x14004243d  mov     ecx, 8; cb
0x140042442  call    cs:__imp_CoTaskMemAlloc
0x140042448  mov     [rsi], rax
0x14004244b  lea     r8, aRaw; "RAW"
0x140042452  mov     edx, 4; SizeInWords
0x140042457  mov     rcx, rax; Destination
0x14004245a  call    cs:__imp_wcscpy_s
0x140042460  jmp     short loc_140042465
0x140042462  mov     edi, r14d
0x140042465  mov     rbx, [rbp+57h+Source]
0x140042469  call    cs:__imp_GetProcessHeap
0x14004246f  mov     r8, rbx
0x140042472  xor     edx, edx
0x140042474  mov     rcx, rax
0x140042477  call    cs:__imp_VdsHeapFree
0x14004247d  mov     [rbp+57h+Source], r14
0x140042481  mov     rcx, [rbp+57h+hObject]; hObject
0x140042485  lea     rax, [rcx-1]
0x140042489  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14004248d  ja      short loc_140042499
0x14004248f  call    cs:__imp_CloseHandle
0x140042495  mov     [rbp+57h+hObject], r14
0x140042499  mov     rcx, [rbp+57h+var_58.pwszName]; pv
0x14004249d  test    rcx, rcx
0x1400424a0  jz      short loc_1400424AC
0x1400424a2  call    cs:__imp_CoTaskMemFree
0x1400424a8  mov     [rbp+57h+var_58.pwszName], r14
0x1400424ac  lea     rcx, [rbp+57h+var_68]
0x1400424b0  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400424b6  mov     eax, edi
0x1400424b8  mov     rcx, [rbp+57h+var_20]
0x1400424bc  xor     rcx, rsp; StackCookie
0x1400424bf  call    __security_check_cookie
0x1400424c4  lea     r11, [rsp+0A0h+var_10]
0x1400424cc  mov     rbx, [r11+30h]
0x1400424d0  mov     rsi, [r11+38h]
0x1400424d4  mov     rsp, r11
0x1400424d7  pop     r14
0x1400424d9  pop     rdi
0x1400424da  pop     rbp
0x1400424db  retn
```
