# CVdsPack::AddDisk(_GUID,_VDS_PARTITION_STYLE,int)

- ea: `0x140013f50`
- end: `0x140014307`
- name: `?AddDisk@CVdsPack@@UEAAJU_GUID@@W4_VDS_PARTITION_STYLE@@H@Z`
- size: `951`
- prototype: `__int64 __fastcall(CVdsPack *this, struct _GUID *, unsigned int, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x140003710`
- `0x140004360`
- `0x14000d6e0`
- `0x140012c48`
- `0x140013298`
- `0x140013f50`
- `0x14003870c`
- `0x14003c424`
- `0x14003c668`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400142c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400142c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140014049`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140014049`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014194`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014194`
- `vdsutil!OpenDevice` at `0x140014129`
- `vdsutil!OpenDevice` at `0x140014129`
- `vdsutil!WriteBootCode` at `0x140014188`
- `vdsutil!WriteBootCode` at `0x140014188`
- `vdsutil!VdsTraceEx` at `0x140014012`
- `vdsutil!VdsTraceEx` at `0x140014074`
- `vdsutil!VdsTraceEx` at `0x1400140b3`
- `vdsutil!VdsTraceEx` at `0x140014144`
- `vdsutil!VdsTraceEx` at `0x1400141bc`
- `vdsutil!VdsTraceEx` at `0x140014251`
- `vdsutil!VdsTraceEx` at `0x14001428c`
- `vdsutil!VdsTraceEx` at `0x140014012`
- `vdsutil!VdsTraceEx` at `0x140014074`
- `vdsutil!VdsTraceEx` at `0x1400140b3`
- `vdsutil!VdsTraceEx` at `0x140014144`
- `vdsutil!VdsTraceEx` at `0x1400141bc`
- `vdsutil!VdsTraceEx` at `0x140014251`
- `vdsutil!VdsTraceEx` at `0x14001428c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140013f9f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140013f9f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140013fcf`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140014027`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400142d7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140013fcf`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140014027`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400142d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CVdsPack::AddDisk(CVdsPack *this, struct _GUID *a2, unsigned int a3, int a4)
{
  int v8; // ebx
  struct CVdsRawDiskLun *RawDisk; // rsi
  int v10; // eax
  __int64 v11; // r9
  unsigned __int16 *v12; // r14
  int v13; // eax
  int v14; // eax
  int Disk; // eax
  int v16; // eax
  int v17; // eax
  struct IVdsProvider *v19; // [rsp+40h] [rbp-59h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-51h] BYREF
  struct IUnknown *v21; // [rsp+50h] [rbp-49h] BYREF
  __int64 v22; // [rsp+58h] [rbp-41h] BYREF
  int v23; // [rsp+60h] [rbp-39h]
  unsigned int v24; // [rsp+68h] [rbp-31h] BYREF
  __int64 v25[2]; // [rsp+70h] [rbp-29h] BYREF
  struct _GUID v26; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int16 *v27; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v28[88]; // [rsp+98h] [rbp-1h] BYREF

  v27 = 0;
  v24 = 0;
  v21 = 0;
  hObject = 0;
  v25[0] = 0;
  v19 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v28, 0x5Eu, "CVdsPack::AddDisk()");
  v22 = 1;
  v23 = 0;
  v8 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v22);
  if ( v8 >= 0 )
  {
    v26 = *a2;
    RawDisk = CVdsService::FindRawDisk(&v26, &v27, &v24);
    if ( RawDisk )
    {
      EnterCriticalSection(&g_GlobalCriticalSection);
      (*(void (__fastcall **)(struct CVdsRawDiskLun *))(*(_QWORD *)RawDisk + 8LL))(RawDisk);
      if ( *((_DWORD *)RawDisk + 86) )
      {
        VdsTraceEx(94, 0, "CVdsPack::AddDisk, 2");
        v8 = -2147211944;
      }
      else
      {
        v10 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 11))(
                *((_QWORD *)this + 11),
                &IID_IVdsMigrateDisks,
                v25);
        v8 = v10;
        if ( v10 >= 0 )
        {
          v26 = *a2;
          v11 = a3;
          v12 = v27;
          v13 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, unsigned __int16 *, __int64, int))(*(_QWORD *)v25[0] + 88LL))(
                  v25[0],
                  &v26,
                  v27,
                  v11,
                  a4);
          v8 = v13;
          if ( v13 >= 0 )
          {
            v14 = OpenDevice(v12, 3221225472LL, &hObject);
            v8 = v14;
            if ( v14 )
            {
              VdsTraceEx(94, 0, "CVdsPack::AddDisk, 5: %ld", v14);
              VdsLogError(0xC2000008, 0, 0, v8, 0x2070007u, v12, 0);
              if ( v8 > 0 )
                v8 = (unsigned __int16)v8 | 0x80070000;
            }
            else
            {
              v8 = WriteBootCode(hObject);
              CloseHandle(hObject);
              hObject = 0;
              if ( v8 )
              {
                if ( v8 > 0 )
                  v8 = (unsigned __int16)v8 | 0x80070000;
                VdsTraceEx(94, 0, "CVdsPack::AddDisk, 6: %lX", v8);
                VdsLogError(0xC200000A, 0, 0, v8, 0x2070008u, 0);
              }
              else
              {
                v26 = *a2;
                Disk = CVdsService::GetDisk(&v26, &v21);
                v8 = Disk;
                if ( Disk >= 0 )
                {
                  v16 = (*(__int64 (__fastcall **)(_QWORD, struct IVdsProvider **))(**((_QWORD **)this + 11) + 32LL))(
                          *((_QWORD *)this + 11),
                          &v19);
                  v8 = v16;
                  if ( v16 >= 0 )
                  {
                    v17 = CVdsService::ResetDiskWrapper(a2, v21, v19, 0);
                    v8 = v17;
                    if ( v17 >= 0 )
                    {
                      v26 = *a2;
                      if ( !CVdsService::RemoveRawDisk(&v26, 0xAu) )
                      {
                        v8 = -2147211946;
                        VdsTraceEx(94, 0, "CVdsPack::AddDisk, 10: %lX", 2147755350LL);
                      }
                    }
                    else
                    {
                      VdsTraceEx(94, 0, "CVdsPack::AddDisk, 9: %lX", v17);
                      v8 = -2147211946;
                    }
                  }
                  else
                  {
                    VdsTraceEx(94, 0, "CVdsPack::AddDisk, 8: %X", (unsigned int)v16);
                  }
                }
                else
                {
                  VdsTraceEx(94, 0, "CVdsPack::AddDisk, 7: %lX", (unsigned int)Disk);
                }
              }
            }
          }
          else
          {
            VdsTraceEx(94, 0, "CVdsPack::AddDisk, 4: %lX", (unsigned int)v13);
          }
        }
        else
        {
          VdsTraceEx(94, 0, "CVdsPack::AddDisk, 3: %lX", v10);
          VdsLogError(0xC2000009, 0, 0, v8, 0x2070006u, 0);
        }
      }
      if ( v21 )
      {
        ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->Release)(v21);
        v21 = 0;
      }
      (*(void (__fastcall **)(struct CVdsRawDiskLun *))(*(_QWORD *)RawDisk + 16LL))(RawDisk);
      LeaveCriticalSection(&g_GlobalCriticalSection);
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v22);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
    }
    else
    {
      VdsTraceEx(94, 0, "CVdsPack::AddDisk, 1");
      CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v22);
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
      v8 = -2147212264;
    }
  }
  else
  {
    CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v22);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v28);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v19);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v25);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140013f50  push    rbp
0x140013f52  push    rbx
0x140013f53  push    rsi
0x140013f54  push    rdi
0x140013f55  push    r12
0x140013f57  push    r13
0x140013f59  push    r14
0x140013f5b  push    r15
0x140013f5d  lea     rbp, [rsp-1Fh]
0x140013f62  sub     rsp, 0B8h
0x140013f69  mov     r12d, r9d
0x140013f6c  mov     r14d, r8d
0x140013f6f  mov     rdi, rdx
0x140013f72  mov     r15, rcx
0x140013f75  xor     r13d, r13d
0x140013f78  mov     [rbp+57h+var_60], r13
0x140013f7c  mov     [rbp+57h+var_88], r13d
0x140013f80  mov     [rbp+57h+var_A0], r13
0x140013f84  mov     [rbp+57h+hObject], r13
0x140013f88  mov     [rbp+57h+var_80], r13
0x140013f8c  mov     [rbp+57h+var_B0], r13
0x140013f90  lea     r8, aCvdspackAdddis_1; "CVdsPack::AddDisk()"
0x140013f97  lea     edx, [r13+5Eh]
0x140013f9b  lea     rcx, [rbp+57h+var_58]
0x140013f9f  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140013fa5  nop
0x140013fa6  mov     [rbp+57h+var_98], 1
0x140013fae  mov     [rbp+57h+var_90], r13d
0x140013fb2  lea     rcx, [rbp+57h+var_98]; this
0x140013fb6  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140013fbb  mov     ebx, eax
0x140013fbd  test    eax, eax
0x140013fbf  jns     short loc_140013FE5
0x140013fc1  lea     rcx, [rbp+57h+var_98]; this
0x140013fc5  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140013fca  nop
0x140013fcb  lea     rcx, [rbp+57h+var_58]
0x140013fcf  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140013fd5  nop
0x140013fd6  lea     rcx, [rbp+57h+var_B0]
0x140013fda  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140013fdf  nop
0x140013fe0  jmp     loc_1400142E8
0x140013fe5  movups  xmm0, xmmword ptr [rdi]
0x140013fe8  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x140013fed  lea     r8, [rbp+57h+var_88]; unsigned int *
0x140013ff1  lea     rdx, [rbp+57h+var_60]; unsigned __int16 **
0x140013ff5  lea     rcx, [rbp+57h+var_70]; struct _GUID
0x140013ff9  call    ?FindRawDisk@CVdsService@@SAPEAVCVdsRawDiskLun@@U_GUID@@AEAPEAGAEAK@Z; CVdsService::FindRawDisk(_GUID,ushort * &,ulong &)
0x140013ffe  mov     rsi, rax
0x140014001  test    rax, rax
0x140014004  jnz     short loc_140014042
0x140014006  lea     r8, aCvdspackAdddis; "CVdsPack::AddDisk, 1"
0x14001400d  xor     edx, edx
0x14001400f  lea     ecx, [rax+5Eh]
0x140014012  call    cs:__imp_VdsTraceEx
0x140014018  nop
0x140014019  lea     rcx, [rbp+57h+var_98]; this
0x14001401d  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140014022  nop
0x140014023  lea     rcx, [rbp+57h+var_58]
0x140014027  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14001402d  nop
0x14001402e  lea     rcx, [rbp+57h+var_B0]
0x140014032  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140014037  nop
0x140014038  mov     ebx, 80042418h
0x14001403d  jmp     loc_1400142E8
0x140014042  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140014049  call    cs:__imp_EnterCriticalSection
0x14001404f  nop
0x140014050  mov     rax, [rsi]
0x140014053  mov     rcx, rsi
0x140014056  mov     rax, [rax+8]
0x14001405a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001405f  cmp     [rsi+158h], r13d
0x140014066  jz      short loc_140014084
0x140014068  lea     r8, aCvdspackAdddis_2; "CVdsPack::AddDisk, 2"
0x14001406f  xor     edx, edx
0x140014071  lea     ecx, [rdx+5Eh]
0x140014074  call    cs:__imp_VdsTraceEx
0x14001407a  mov     ebx, 80042558h
0x14001407f  jmp     loc_140014292
0x140014084  mov     rcx, [r15+58h]
0x140014088  mov     rax, [rcx]
0x14001408b  lea     r8, [rbp+57h+var_80]
0x14001408f  lea     rdx, IID_IVdsMigrateDisks
0x140014096  mov     rax, [rax]
0x140014099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001409e  mov     ebx, eax
0x1400140a0  test    eax, eax
0x1400140a2  jns     short loc_1400140DD
0x1400140a4  mov     r9d, eax
0x1400140a7  lea     r8, aCvdspackAdddis_3; "CVdsPack::AddDisk, 3: %lX"
0x1400140ae  xor     edx, edx
0x1400140b0  lea     ecx, [rdx+5Eh]
0x1400140b3  call    cs:__imp_VdsTraceEx
0x1400140b9  mov     [rsp+0F0h+var_C8], r13; unsigned __int16 *
0x1400140be  mov     [rsp+0F0h+var_D0], 2070006h; unsigned int
0x1400140c6  mov     ecx, 0C2000009h; unsigned int
0x1400140cb  xor     r8d, r8d; void *
0x1400140ce  xor     edx, edx; unsigned int
0x1400140d0  mov     r9d, ebx; unsigned int
0x1400140d3  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x1400140d8  jmp     loc_140014292
0x1400140dd  mov     rcx, [rbp+57h+var_80]
0x1400140e1  movups  xmm0, xmmword ptr [rdi]
0x1400140e4  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x1400140e9  mov     rax, [rcx]
0x1400140ec  mov     [rsp+0F0h+var_D0], r12d
0x1400140f1  mov     r9d, r14d
0x1400140f4  mov     r14, [rbp+57h+var_60]
0x1400140f8  mov     r8, r14
0x1400140fb  lea     rdx, [rbp+57h+var_70]
0x1400140ff  mov     rax, [rax+58h]
0x140014103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014108  mov     ebx, eax
0x14001410a  test    eax, eax
0x14001410c  jns     short loc_14001411D
0x14001410e  mov     r9d, eax
0x140014111  lea     r8, aCvdspackAdddis_6; "CVdsPack::AddDisk, 4: %lX"
0x140014118  jmp     loc_140014287
0x14001411d  lea     r8, [rbp+57h+hObject]
0x140014121  mov     edx, 0C0000000h
0x140014126  mov     rcx, r14
0x140014129  call    cs:__imp_OpenDevice
0x14001412f  mov     ebx, eax
0x140014131  test    eax, eax
0x140014133  jz      short loc_140014184
0x140014135  mov     r9d, eax
0x140014138  lea     r8, aCvdspackAdddis_0; "CVdsPack::AddDisk, 5: %ld"
0x14001413f  xor     edx, edx
0x140014141  lea     ecx, [rdx+5Eh]
0x140014144  call    cs:__imp_VdsTraceEx
0x14001414a  mov     [rsp+0F0h+var_C0], r13
0x14001414f  mov     [rsp+0F0h+var_C8], r14; unsigned __int16 *
0x140014154  mov     [rsp+0F0h+var_D0], 2070007h; unsigned int
0x14001415c  mov     r9d, ebx; unsigned int
0x14001415f  xor     r8d, r8d; void *
0x140014162  xor     edx, edx; unsigned int
0x140014164  mov     ecx, 0C2000008h; unsigned int
0x140014169  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x14001416e  test    ebx, ebx
0x140014170  jle     loc_140014292
0x140014176  movzx   ebx, bx
0x140014179  or      ebx, 80070000h
0x14001417f  jmp     loc_140014292
0x140014184  mov     rcx, [rbp+57h+hObject]
0x140014188  call    cs:__imp_WriteBootCode
0x14001418e  mov     ebx, eax
0x140014190  mov     rcx, [rbp+57h+hObject]; hObject
0x140014194  call    cs:__imp_CloseHandle
0x14001419a  mov     [rbp+57h+hObject], r13
0x14001419e  test    ebx, ebx
0x1400141a0  jz      short loc_1400141D9
0x1400141a2  jle     short loc_1400141AD
0x1400141a4  movzx   ebx, bx
0x1400141a7  or      ebx, 80070000h
0x1400141ad  mov     r9d, ebx
0x1400141b0  lea     r8, aCvdspackAdddis_5; "CVdsPack::AddDisk, 6: %lX"
0x1400141b7  xor     edx, edx
0x1400141b9  lea     ecx, [rdx+5Eh]
0x1400141bc  call    cs:__imp_VdsTraceEx
0x1400141c2  mov     [rsp+0F0h+var_C8], r13
0x1400141c7  mov     [rsp+0F0h+var_D0], 2070008h
0x1400141cf  mov     ecx, 0C200000Ah
0x1400141d4  jmp     loc_1400140CB
0x1400141d9  movups  xmm0, xmmword ptr [rdi]
0x1400141dc  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x1400141e1  lea     rdx, [rbp+57h+var_A0]; struct IUnknown **
0x1400141e5  lea     rcx, [rbp+57h+var_70]; struct _GUID
0x1400141e9  call    ?GetDisk@CVdsService@@SAJU_GUID@@PEAPEAUIUnknown@@@Z; CVdsService::GetDisk(_GUID,IUnknown * *)
0x1400141ee  mov     ebx, eax
0x1400141f0  test    eax, eax
0x1400141f2  jns     short loc_140014203
0x1400141f4  mov     r9d, eax
0x1400141f7  lea     r8, aCvdspackAdddis_7; "CVdsPack::AddDisk, 7: %lX"
0x1400141fe  jmp     loc_140014287
0x140014203  mov     rcx, [r15+58h]
0x140014207  mov     rax, [rcx]
0x14001420a  lea     rdx, [rbp+57h+var_B0]
0x14001420e  mov     rax, [rax+20h]
0x140014212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014217  mov     ebx, eax
0x140014219  test    eax, eax
0x14001421b  jns     short loc_140014229
0x14001421d  mov     r9d, eax
0x140014220  lea     r8, aCvdspackAdddis_9; "CVdsPack::AddDisk, 8: %X"
0x140014227  jmp     short loc_140014287
0x140014229  xor     r9d, r9d; int
0x14001422c  mov     r8, [rbp+57h+var_B0]; struct IVdsProvider *
0x140014230  mov     rdx, [rbp+57h+var_A0]; struct IUnknown *
0x140014234  mov     rcx, rdi; struct _GUID *
0x140014237  call    ?ResetDiskWrapper@CVdsService@@SAJAEAU_GUID@@PEAUIUnknown@@PEAUIVdsProvider@@H@Z; CVdsService::ResetDiskWrapper(_GUID &,IUnknown *,IVdsProvider *,int)
0x14001423c  mov     ebx, eax
0x14001423e  test    eax, eax
0x140014240  jns     short loc_14001425E
0x140014242  mov     r9d, eax
0x140014245  lea     r8, aCvdspackAdddis_4; "CVdsPack::AddDisk, 9: %lX"
0x14001424c  xor     edx, edx
0x14001424e  lea     ecx, [rdx+5Eh]
0x140014251  call    cs:__imp_VdsTraceEx
0x140014257  mov     ebx, 80042556h
0x14001425c  jmp     short loc_140014292
0x14001425e  movups  xmm0, xmmword ptr [rdi]
0x140014261  movdqu  xmmword ptr [rbp+57h+var_70.Data1], xmm0
0x140014266  mov     edx, 0Ah; unsigned int
0x14001426b  lea     rcx, [rbp+57h+var_70]; struct _GUID
0x14001426f  call    ?RemoveRawDisk@CVdsService@@SAHU_GUID@@K@Z; CVdsService::RemoveRawDisk(_GUID,ulong)
0x140014274  test    eax, eax
0x140014276  jnz     short loc_140014292
0x140014278  mov     ebx, 80042556h
0x14001427d  mov     r9d, ebx
0x140014280  lea     r8, aCvdspackAdddis_8; "CVdsPack::AddDisk, 10: %lX"
0x140014287  xor     edx, edx
0x140014289  lea     ecx, [rdx+5Eh]
0x14001428c  call    cs:__imp_VdsTraceEx
0x140014292  mov     rcx, [rbp+57h+var_A0]
0x140014296  test    rcx, rcx
0x140014299  jz      short loc_1400142AB
0x14001429b  mov     rax, [rcx]
0x14001429e  mov     rax, [rax+10h]
0x1400142a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400142a7  mov     [rbp+57h+var_A0], r13
0x1400142ab  mov     rax, [rsi]
0x1400142ae  mov     rcx, rsi
0x1400142b1  mov     rax, [rax+10h]
0x1400142b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400142ba  nop
0x1400142bb  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400142c2  call    cs:__imp_LeaveCriticalSection
0x1400142c8  nop
0x1400142c9  lea     rcx, [rbp+57h+var_98]; this
0x1400142cd  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x1400142d2  nop
0x1400142d3  lea     rcx, [rbp+57h+var_58]
0x1400142d7  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400142dd  nop
0x1400142de  lea     rcx, [rbp+57h+var_B0]
0x1400142e2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400142e7  nop
0x1400142e8  lea     rcx, [rbp+57h+var_80]
0x1400142ec  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400142f1  mov     eax, ebx
0x1400142f3  add     rsp, 0B8h
0x1400142fa  pop     r15
0x1400142fc  pop     r14
0x1400142fe  pop     r13
0x140014300  pop     r12
0x140014302  pop     rdi
0x140014303  pop     rsi
0x140014304  pop     rbx
0x140014305  pop     rbp
0x140014306  retn
```
