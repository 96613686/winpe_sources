# CVdsDiskLun::QueryPartitionFileSystemFormatSupport(unsigned __int64,_VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP * *,long *)

- ea: `0x1400210b0`
- end: `0x140021256`
- name: `?QueryPartitionFileSystemFormatSupport@CVdsDiskLun@@UEAAJ_KPEAPEAU_VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP@@PEAJ@Z`
- size: `422`
- prototype: `int(CVdsDiskLun *__hidden this, unsigned __int64, struct _VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP **, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x140005b1c`
- `0x1400210b0`
- `0x1400446d8`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002121d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002121d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140021135`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140021135`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140021208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140021208`
- `vdsutil!OpenDevice` at `0x1400211a2`
- `vdsutil!OpenDevice` at `0x1400211a2`
- `vdsutil!VdsTraceEx` at `0x14002115a`
- `vdsutil!VdsTraceEx` at `0x14002115a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400210ef`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400210ef`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140021232`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140021232`
- `vdsutil!VdsTraceW` at `0x1400211be`
- `vdsutil!VdsTraceW` at `0x1400211f4`
- `vdsutil!VdsTraceW` at `0x1400211be`
- `vdsutil!VdsTraceW` at `0x1400211f4`

## string_xrefs

- `0x1400211b5`: `CVdsDiskLun::QueryPartitionFileSystemFormatSupport: failed to open device (%s), error=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::QueryPartitionFileSystemFormatSupport(
        CVdsDiskLun *this,
        __int64 a2,
        struct _VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP **a3,
        int *a4)
{
  int v8; // ebx
  int v9; // eax
  __int64 v10; // r8
  int v11; // eax
  unsigned int v12; // eax
  int FileSystemFormatSupportInternal; // eax
  HANDLE hObject; // [rsp+20h] [rbp-69h] BYREF
  __int64 v16; // [rsp+28h] [rbp-61h] BYREF
  int v17; // [rsp+30h] [rbp-59h]
  _BYTE v18[24]; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 v19[44]; // [rsp+50h] [rbp-39h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v18, 0x5Eu, "CVdsDiskLun::QueryPartitionFileSystemFormatSupport()");
  hObject = 0;
  *a3 = 0;
  *a4 = 0;
  v16 = 0;
  v17 = 0;
  v8 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v16);
  if ( v8 >= 0 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    v9 = CVdsDiskLun::ValidateDiskInterfaces((CVdsDiskLun *)((char *)this - 64));
    v8 = v9;
    if ( v9 >= 0 )
    {
      v11 = CVdsDiskLun::BuildOEMPartitionName((CVdsDiskLun *)((char *)this - 64), a2, v10, v19);
      v8 = v11;
      if ( v11 >= 0 )
      {
        v12 = OpenDevice(v19, 0x80000000LL, &hObject);
        v8 = v12;
        if ( v12 )
        {
          VdsTraceW(
            0,
            L"CVdsDiskLun::QueryPartitionFileSystemFormatSupport: failed to open device (%s), error=%lX",
            v19,
            v12);
          if ( v8 > 0 )
            v8 = (unsigned __int16)v8 | 0x80070000;
        }
        else
        {
          FileSystemFormatSupportInternal = CVdsVolume::QueryFileSystemFormatSupportInternal(hObject, a3, a4);
          v8 = FileSystemFormatSupportInternal;
          if ( FileSystemFormatSupportInternal < 0 )
            VdsTraceW(
              0,
              L"CVdsDiskLun::QueryPartitionFileSystemFormatSupport, 3, hr=%lX",
              (unsigned int)FileSystemFormatSupportInternal);
        }
      }
      else
      {
        VdsTraceW(0, L"CVdsDiskLun::QueryPartitionFileSystemFormatSupport, 2, hr=%lX", (unsigned int)v11);
      }
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsDiskLun::QueryPartitionFileSystemFormatSupport, 1, hr=%lX", v9);
      if ( v8 == -2147212283 )
        v8 = -2147212277;
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    LeaveCriticalSection(&g_GlobalCriticalSection);
  }
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v16);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400210b0  push    rbp
0x1400210b2  push    rbx
0x1400210b3  push    rsi
0x1400210b4  push    rdi
0x1400210b5  push    r14
0x1400210b7  push    r15
0x1400210b9  lea     rbp, [rsp-2Fh]
0x1400210be  sub     rsp, 0B8h
0x1400210c5  mov     rax, cs:__security_cookie
0x1400210cc  xor     rax, rsp
0x1400210cf  mov     [rbp+57h+var_38], rax
0x1400210d3  mov     r14, r9
0x1400210d6  mov     rsi, r8
0x1400210d9  mov     r15, rdx
0x1400210dc  mov     rdi, rcx
0x1400210df  lea     r8, aCvdsdisklunQue_50; "CVdsDiskLun::QueryPartitionFileSystemFo"...
0x1400210e6  mov     edx, 5Eh ; '^'
0x1400210eb  lea     rcx, [rbp+57h+var_A8]
0x1400210ef  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400210f5  nop
0x1400210f6  mov     [rbp+57h+hObject], 0
0x1400210fe  mov     qword ptr [rsi], 0
0x140021105  mov     dword ptr [r14], 0
0x14002110c  mov     [rbp+57h+var_B8], 0
0x140021114  mov     [rbp+57h+var_B0], 0
0x14002111b  lea     rcx, [rbp+57h+var_B8]; this
0x14002111f  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140021124  mov     ebx, eax
0x140021126  test    eax, eax
0x140021128  js      loc_140021224
0x14002112e  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140021135  call    cs:__imp_EnterCriticalSection
0x14002113b  nop
0x14002113c  lea     rcx, [rdi-40h]; this
0x140021140  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140021145  mov     ebx, eax
0x140021147  test    eax, eax
0x140021149  jns     short loc_140021176
0x14002114b  mov     r9d, eax
0x14002114e  lea     r8, aCvdsdisklunQue_46; "CVdsDiskLun::QueryPartitionFileSystemFo"...
0x140021155  xor     edx, edx
0x140021157  lea     ecx, [rdx+5Eh]
0x14002115a  call    cs:__imp_VdsTraceEx
0x140021160  cmp     ebx, 80042405h
0x140021166  jnz     loc_1400211FA
0x14002116c  mov     ebx, 8004240Bh
0x140021171  jmp     loc_1400211FA
0x140021176  lea     r9, [rbp+57h+var_90]; unsigned __int16 *
0x14002117a  mov     rdx, r15; unsigned __int64
0x14002117d  lea     rcx, [rdi-40h]; this
0x140021181  call    ?BuildOEMPartitionName@CVdsDiskLun@@AEAAJ_KKPEAG@Z; CVdsDiskLun::BuildOEMPartitionName(unsigned __int64,ulong,ushort *)
0x140021186  mov     ebx, eax
0x140021188  test    eax, eax
0x14002118a  jns     short loc_140021195
0x14002118c  lea     rdx, aCvdsdisklunQue_27; "CVdsDiskLun::QueryPartitionFileSystemFo"...
0x140021193  jmp     short loc_1400211EF
0x140021195  lea     r8, [rbp+57h+hObject]
0x140021199  mov     edx, 80000000h
0x14002119e  lea     rcx, [rbp+57h+var_90]
0x1400211a2  call    cs:__imp_OpenDevice
0x1400211a8  mov     ebx, eax
0x1400211aa  test    eax, eax
0x1400211ac  jz      short loc_1400211D3
0x1400211ae  mov     r9d, eax
0x1400211b1  lea     r8, [rbp+57h+var_90]
0x1400211b5  lea     rdx, aCvdsdisklunQue_43; "CVdsDiskLun::QueryPartitionFileSystemFo"...
0x1400211bc  xor     ecx, ecx
0x1400211be  call    cs:__imp_VdsTraceW
0x1400211c4  test    ebx, ebx
0x1400211c6  jle     short loc_1400211FA
0x1400211c8  movzx   ebx, bx
0x1400211cb  or      ebx, 80070000h
0x1400211d1  jmp     short loc_1400211FA
0x1400211d3  mov     r8, r14; int *
0x1400211d6  mov     rdx, rsi; struct _VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP **
0x1400211d9  mov     rcx, [rbp+57h+hObject]; void *
0x1400211dd  call    ?QueryFileSystemFormatSupportInternal@CVdsVolume@@SAJPEAXPEAPEAU_VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP@@PEAJ@Z; CVdsVolume::QueryFileSystemFormatSupportInternal(void *,_VDS_FILE_SYSTEM_FORMAT_SUPPORT_PROP * *,long *)
0x1400211e2  mov     ebx, eax
0x1400211e4  test    eax, eax
0x1400211e6  jns     short loc_1400211FA
0x1400211e8  lea     rdx, aCvdsdisklunQue_7; "CVdsDiskLun::QueryPartitionFileSystemFo"...
0x1400211ef  mov     r8d, eax
0x1400211f2  xor     ecx, ecx
0x1400211f4  call    cs:__imp_VdsTraceW
0x1400211fa  mov     rcx, [rbp+57h+hObject]; hObject
0x1400211fe  lea     rax, [rcx-1]
0x140021202  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140021206  ja      short loc_140021216
0x140021208  call    cs:__imp_CloseHandle
0x14002120e  mov     [rbp+57h+hObject], 0
0x140021216  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002121d  call    cs:__imp_LeaveCriticalSection
0x140021223  nop
0x140021224  lea     rcx, [rbp+57h+var_B8]; this
0x140021228  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x14002122d  nop
0x14002122e  lea     rcx, [rbp+57h+var_A8]
0x140021232  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140021238  mov     eax, ebx
0x14002123a  mov     rcx, [rbp+57h+var_38]
0x14002123e  xor     rcx, rsp; StackCookie
0x140021241  call    __security_check_cookie
0x140021246  add     rsp, 0B8h
0x14002124d  pop     r15
0x14002124f  pop     r14
0x140021251  pop     rdi
0x140021252  pop     rsi
0x140021253  pop     rbx
0x140021254  pop     rbp
0x140021255  retn
```
