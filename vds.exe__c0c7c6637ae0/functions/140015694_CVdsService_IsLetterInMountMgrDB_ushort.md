# CVdsService::IsLetterInMountMgrDB(ushort)

- ea: `0x140015694`
- end: `0x14001593d`
- name: `?IsLetterInMountMgrDB@CVdsService@@SAJG@Z`
- size: `681`
- prototype: `__int64 __fastcall(unsigned __int16)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting, service_task`

## callers

- `0x140028340`

## callees

- `0x1400069e8`
- `0x14000d0f0`
- `0x14000f930`
- `0x14000f9b0`
- `0x140015694`
- `0x140015dd0`
- `0x14002de26`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001574f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001583d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001574f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001583d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001589a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400158a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001589a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400158a7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400157e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400157e7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140015890`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140015890`
- `vdsutil!VdsHeapAlloc` at `0x140015760`
- `vdsutil!VdsHeapAlloc` at `0x14001584e`
- `vdsutil!VdsHeapAlloc` at `0x140015760`
- `vdsutil!VdsHeapAlloc` at `0x14001584e`
- `vdsutil!VdsTraceEx` at `0x14001572b`
- `vdsutil!VdsTraceEx` at `0x140015817`
- `vdsutil!VdsTraceEx` at `0x1400158c6`
- `vdsutil!VdsTraceEx` at `0x1400158e8`
- `vdsutil!VdsTraceEx` at `0x14001572b`
- `vdsutil!VdsTraceEx` at `0x140015817`
- `vdsutil!VdsTraceEx` at `0x1400158c6`
- `vdsutil!VdsTraceEx` at `0x1400158e8`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400156e8`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400156e8`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400158f7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400158f7`

## string_xrefs

- `0x1400157e0`: `\\.\MountPointManager`
- `0x14001580b`: `CVdsService::IsLetterInMountMgrDB, 4, error=%ld`
- `0x1400156d5`: `CVdsService::IsLetterInMountMgrDB()`
- `0x14001571f`: `CVdsService::IsLetterInMountMgrDB, 1, hr=%lX`
- `0x14001577b`: `CVdsService::IsLetterInMountMgrDB, 2`
- `0x1400158dc`: `CVdsService::IsLetterInMountMgrDB, 5`
- `0x1400158b5`: `CVdsService::IsLetterInMountMgrDB, 6, (%S): error=%ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVdsService::IsLetterInMountMgrDB(unsigned __int16 a1)
{
  unsigned int v1; // ebx
  int v2; // eax
  signed int LastError; // esi
  __int64 v4; // r14
  DWORD v5; // r15d
  HANDLE ProcessHeap; // rax
  __int64 v7; // rax
  unsigned int *v8; // rdi
  HANDLE FileW; // rax
  DWORD v10; // r14d
  HANDLE v11; // rax
  __int64 v12; // rax
  _WORD *v13; // rbx
  DWORD v14; // eax
  HANDLE hDevice; // [rsp+40h] [rbp-49h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-41h] BYREF
  LPVOID lpOutBuffer; // [rsp+50h] [rbp-39h] BYREF
  LPVOID lpInBuffer; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v20[16]; // [rsp+60h] [rbp-29h] BYREF
  _OWORD Src[2]; // [rsp+70h] [rbp-19h] BYREF
  __int64 v22; // [rsp+90h] [rbp+7h]

  v1 = a1;
  lpInBuffer = 0;
  lpOutBuffer = 0;
  hDevice = (HANDLE)-1LL;
  BytesReturned = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v20, 0x5Eu, "CVdsService::IsLetterInMountMgrDB()");
  memset(Src, 0, sizeof(Src));
  v22 = 0;
  v2 = StringCchPrintfW((unsigned __int16 *)Src, 0x14u, L"\\DosDevices\\%c:", v1);
  LastError = v2;
  if ( v2 >= 0 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *((_WORD *)Src + v4) );
    v5 = 2 * v4 + 24;
    ProcessHeap = GetProcessHeap();
    v7 = VdsHeapAlloc(ProcessHeap, 8, v5);
    CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=((__int64 *)&lpInBuffer, v7);
    v8 = (unsigned int *)lpInBuffer;
    if ( lpInBuffer )
    {
      *(_DWORD *)lpInBuffer = 24;
      *((_WORD *)v8 + 2) = 2 * v4;
      v8[2] = 0;
      *((_WORD *)v8 + 6) = 0;
      v8[4] = 0;
      *((_WORD *)v8 + 10) = 0;
      memcpy_0((char *)v8 + *v8, Src, 2 * v4);
      FileW = CreateFileW(L"\\\\.\\MountPointManager", 0xC0000000, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      CVdsHandleImpl<-1>::operator=(&hDevice, FileW);
      if ( hDevice == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        VdsTraceEx(94, 0, "CVdsService::IsLetterInMountMgrDB, 4, error=%ld", LastError);
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v10 = 0;
        while ( 1 )
        {
          v10 += 256;
          v11 = GetProcessHeap();
          v12 = VdsHeapAlloc(v11, 8, v10);
          CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=((__int64 *)&lpOutBuffer, v12);
          v13 = lpOutBuffer;
          if ( !lpOutBuffer )
          {
            VdsTraceEx(94, 0, "CVdsService::IsLetterInMountMgrDB, 5");
            goto LABEL_18;
          }
          if ( DeviceIoControl(hDevice, 0x6D0008u, v8, v5, lpOutBuffer, v10, &BytesReturned, 0) )
            break;
          if ( GetLastError() != 234 )
          {
            v14 = GetLastError();
            LastError = 1;
            VdsTraceEx(94, 1, "CVdsService::IsLetterInMountMgrDB, 6, (%S): error=%ld", (const wchar_t *)Src, v14);
            goto LABEL_19;
          }
        }
        if ( !v13[10] )
          LastError = 1;
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsService::IsLetterInMountMgrDB, 2");
LABEL_18:
      LastError = -2147024882;
    }
  }
  else
  {
    VdsTraceEx(94, 0, "CVdsService::IsLetterInMountMgrDB, 1, hr=%lX", v2);
  }
LABEL_19:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v20);
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&hDevice);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpOutBuffer);
  CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>((__int64 *)&lpInBuffer);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140015694  push    rbp
0x140015696  push    rbx
0x140015697  push    rsi
0x140015698  push    rdi
0x140015699  push    r12
0x14001569b  push    r13
0x14001569d  push    r14
0x14001569f  push    r15
0x1400156a1  lea     rbp, [rsp-1Fh]
0x1400156a6  sub     rsp, 0A8h
0x1400156ad  mov     rax, cs:__security_cookie
0x1400156b4  xor     rax, rsp
0x1400156b7  mov     [rbp+57h+var_48], rax
0x1400156bb  movzx   ebx, cx
0x1400156be  xor     r12d, r12d
0x1400156c1  mov     [rbp+57h+lpInBuffer], r12
0x1400156c5  mov     [rbp+57h+lpOutBuffer], r12
0x1400156c9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400156cd  mov     [rbp+57h+hDevice], rdi
0x1400156d1  mov     [rbp+57h+BytesReturned], r12d
0x1400156d5  lea     r8, aCvdsserviceIsl_0; "CVdsService::IsLetterInMountMgrDB()"
0x1400156dc  lea     r13d, [r12+5Eh]
0x1400156e1  mov     edx, r13d
0x1400156e4  lea     rcx, [rbp+57h+var_80]
0x1400156e8  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400156ee  nop
0x1400156ef  xorps   xmm0, xmm0
0x1400156f2  xor     eax, eax
0x1400156f4  movups  [rbp+57h+Src], xmm0
0x1400156f8  movups  [rbp+57h+var_60], xmm0
0x1400156fc  mov     [rbp+57h+var_50], rax
0x140015700  mov     r9d, ebx
0x140015703  lea     r8, aDosdevicesC; "\\DosDevices\\%c:"
0x14001570a  lea     edx, [rdi+15h]; unsigned __int64
0x14001570d  lea     rcx, [rbp+57h+Src]; unsigned __int16 *
0x140015711  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140015716  mov     esi, eax
0x140015718  test    eax, eax
0x14001571a  jns     short loc_140015736
0x14001571c  mov     r9d, eax
0x14001571f  lea     r8, aCvdsserviceIsl_2; "CVdsService::IsLetterInMountMgrDB, 1, h"...
0x140015726  xor     edx, edx
0x140015728  mov     ecx, r13d
0x14001572b  call    cs:__imp_VdsTraceEx
0x140015731  jmp     loc_1400158F3
0x140015736  lea     rax, [rbp+57h+Src]
0x14001573a  mov     r14, rdi
0x14001573d  inc     r14
0x140015740  cmp     [rax+r14*2], r12w
0x140015745  jnz     short loc_14001573D
0x140015747  lea     r15d, ds:18h[r14*2]
0x14001574f  call    cs:__imp_GetProcessHeap
0x140015755  mov     rcx, rax
0x140015758  mov     r8d, r15d
0x14001575b  mov     edx, 8
0x140015760  call    cs:__imp_VdsHeapAlloc
0x140015766  mov     rdx, rax
0x140015769  lea     rcx, [rbp+57h+lpInBuffer]
0x14001576d  call    ??4?$CVdsHeapPtr@U_MOUNTMGR_MOUNT_POINT@@@@QEAAPEAU_MOUNTMGR_MOUNT_POINT@@PEAU1@@Z; CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=(_MOUNTMGR_MOUNT_POINT *)
0x140015772  mov     rdi, [rbp+57h+lpInBuffer]
0x140015776  test    rdi, rdi
0x140015779  jnz     short loc_140015787
0x14001577b  lea     r8, aCvdsserviceIsl_3; "CVdsService::IsLetterInMountMgrDB, 2"
0x140015782  jmp     loc_1400158E3
0x140015787  mov     dword ptr [rdi], 18h
0x14001578d  movzx   eax, r14w
0x140015791  add     ax, ax
0x140015794  mov     [rdi+4], ax
0x140015798  mov     [rdi+8], r12d
0x14001579c  mov     [rdi+0Ch], r12w
0x1400157a1  mov     [rdi+10h], r12d
0x1400157a5  mov     [rdi+14h], r12w
0x1400157aa  lea     r8, [r14+r14]; Size
0x1400157ae  mov     ecx, [rdi]
0x1400157b0  add     rcx, rdi; void *
0x1400157b3  lea     rdx, [rbp+57h+Src]; Src
0x1400157b7  call    memcpy_0
0x1400157bc  mov     [rsp+0E0h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x1400157c5  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400157cd  mov     r8d, 3; dwShareMode
0x1400157d3  mov     [rsp+0E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400157d8  xor     r9d, r9d; lpSecurityAttributes
0x1400157db  mov     edx, 0C0000000h; dwDesiredAccess
0x1400157e0  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x1400157e7  call    cs:__imp_CreateFileW
0x1400157ed  mov     rdx, rax
0x1400157f0  lea     rcx, [rbp+57h+hDevice]
0x1400157f4  call    ??4?$CVdsHandleImpl@$0?0@@QEAAPEAXPEAX@Z; CVdsHandleImpl<-1>::operator=(void *)
0x1400157f9  cmp     [rbp+57h+hDevice], 0FFFFFFFFFFFFFFFFh
0x1400157fe  jnz     short loc_140015833
0x140015800  call    cs:__imp_GetLastError
0x140015806  mov     esi, eax
0x140015808  mov     r9d, eax
0x14001580b  lea     r8, aCvdsserviceIsl_4; "CVdsService::IsLetterInMountMgrDB, 4, e"...
0x140015812  xor     edx, edx
0x140015814  mov     ecx, r13d
0x140015817  call    cs:__imp_VdsTraceEx
0x14001581d  test    esi, esi
0x14001581f  jle     loc_1400158F3
0x140015825  movzx   esi, si
0x140015828  or      esi, 80070000h
0x14001582e  jmp     loc_1400158F3
0x140015833  mov     r14d, r12d
0x140015836  add     r14d, 100h
0x14001583d  call    cs:__imp_GetProcessHeap
0x140015843  mov     rcx, rax
0x140015846  mov     r8d, r14d
0x140015849  mov     edx, 8
0x14001584e  call    cs:__imp_VdsHeapAlloc
0x140015854  mov     rdx, rax
0x140015857  lea     rcx, [rbp+57h+lpOutBuffer]
0x14001585b  call    ??4?$CVdsHeapPtr@U_MOUNTMGR_MOUNT_POINT@@@@QEAAPEAU_MOUNTMGR_MOUNT_POINT@@PEAU1@@Z; CVdsHeapPtr<_MOUNTMGR_MOUNT_POINT>::operator=(_MOUNTMGR_MOUNT_POINT *)
0x140015860  mov     rbx, [rbp+57h+lpOutBuffer]
0x140015864  test    rbx, rbx
0x140015867  jz      short loc_1400158DC
0x140015869  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x14001586e  lea     rax, [rbp+57h+BytesReturned]
0x140015872  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x140015877  mov     [rsp+0E0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x14001587c  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rbx; lpOutBuffer
0x140015881  mov     r9d, r15d; nInBufferSize
0x140015884  mov     r8, rdi; lpInBuffer
0x140015887  mov     edx, 6D0008h; dwIoControlCode
0x14001588c  mov     rcx, [rbp+57h+hDevice]; hDevice
0x140015890  call    cs:__imp_DeviceIoControl
0x140015896  test    eax, eax
0x140015898  jnz     short loc_1400158CE
0x14001589a  call    cs:__imp_GetLastError
0x1400158a0  cmp     eax, 0EAh
0x1400158a5  jz      short loc_140015836
0x1400158a7  call    cs:__imp_GetLastError
0x1400158ad  mov     [rsp+0E0h+dwCreationDisposition], eax
0x1400158b1  lea     r9, [rbp+57h+Src]
0x1400158b5  lea     r8, aCvdsserviceIsl; "CVdsService::IsLetterInMountMgrDB, 6, ("...
0x1400158bc  mov     esi, 1
0x1400158c1  mov     edx, esi
0x1400158c3  mov     ecx, r13d
0x1400158c6  call    cs:__imp_VdsTraceEx
0x1400158cc  jmp     short loc_1400158F3
0x1400158ce  cmp     [rbx+14h], r12w
0x1400158d3  jnz     short loc_1400158F3
0x1400158d5  mov     esi, 1
0x1400158da  jmp     short loc_1400158F3
0x1400158dc  lea     r8, aCvdsserviceIsl_1; "CVdsService::IsLetterInMountMgrDB, 5"
0x1400158e3  xor     edx, edx
0x1400158e5  mov     ecx, r13d
0x1400158e8  call    cs:__imp_VdsTraceEx
0x1400158ee  mov     esi, 8007000Eh
0x1400158f3  lea     rcx, [rbp+57h+var_80]
0x1400158f7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400158fd  nop
0x1400158fe  lea     rcx, [rbp+57h+hDevice]
0x140015902  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x140015907  nop
0x140015908  lea     rcx, [rbp+57h+lpOutBuffer]
0x14001590c  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x140015911  nop
0x140015912  lea     rcx, [rbp+57h+lpInBuffer]
0x140015916  call    ??1?$CVdsHeapPtr@U_EXTEND_VOLUME_HANDLER_PARAMETER@@@@QEAA@XZ; CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>::~CVdsHeapPtr<_EXTEND_VOLUME_HANDLER_PARAMETER>(void)
0x14001591b  mov     eax, esi
0x14001591d  mov     rcx, [rbp+57h+var_48]
0x140015921  xor     rcx, rsp; StackCookie
0x140015924  call    __security_check_cookie
0x140015929  add     rsp, 0A8h
0x140015930  pop     r15
0x140015932  pop     r14
0x140015934  pop     r13
0x140015936  pop     r12
0x140015938  pop     rdi
0x140015939  pop     rsi
0x14001593a  pop     rbx
0x14001593b  pop     rbp
0x14001593c  retn
```
