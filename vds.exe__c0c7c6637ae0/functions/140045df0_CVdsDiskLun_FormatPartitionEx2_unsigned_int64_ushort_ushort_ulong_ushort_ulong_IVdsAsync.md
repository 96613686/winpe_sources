# CVdsDiskLun::FormatPartitionEx2(unsigned __int64,ushort *,ushort,ulong,ushort *,ulong,IVdsAsync * *)

- ea: `0x140045df0`
- end: `0x140046049`
- name: `?FormatPartitionEx2@CVdsDiskLun@@UEAAJ_KPEAGGK1KPEAPEAUIVdsAsync@@@Z`
- size: `601`
- prototype: `int(CVdsDiskLun *__hidden this, unsigned __int64, unsigned __int16 *, unsigned __int16, unsigned int, unsigned __int16 *, unsigned int, struct IVdsAsync **)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140003710`
- `0x140004360`
- `0x140005630`
- `0x14002b3f8`
- `0x14002e123`
- `0x1400446d8`
- `0x140045df0`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140046008`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140046008`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140045e95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140045e95`
- `vdsutil!RemoveTempVolumeName` at `0x140045ffa`
- `vdsutil!RemoveTempVolumeName` at `0x140045ffa`
- `vdsutil!AssignTempVolumeName` at `0x140045f38`
- `vdsutil!AssignTempVolumeName` at `0x140045f38`
- `vdsutil!VdsTraceEx` at `0x140045eb5`
- `vdsutil!VdsTraceEx` at `0x140045ee8`
- `vdsutil!VdsTraceEx` at `0x140045eb5`
- `vdsutil!VdsTraceEx` at `0x140045ee8`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140045e48`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140045e48`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004601e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004601e`
- `vdsutil!VdsTraceW` at `0x140045f25`
- `vdsutil!VdsTraceW` at `0x140045f54`
- `vdsutil!VdsTraceW` at `0x140045fdd`
- `vdsutil!VdsTraceW` at `0x140045f25`
- `vdsutil!VdsTraceW` at `0x140045f54`
- `vdsutil!VdsTraceW` at `0x140045fdd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsDiskLun::FormatPartitionEx2(
        CVdsDiskLun *this,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 a4,
        unsigned int a5,
        unsigned __int16 *a6,
        char a7,
        struct IVdsAsync **a8)
{
  signed int v12; // ebx
  CVdsDiskLun *v13; // rdi
  int v14; // eax
  __int64 v15; // r8
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v20; // [rsp+60h] [rbp-A0h] BYREF
  int v21; // [rsp+68h] [rbp-98h]
  struct _GUID v22; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[16]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v24[40]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v25[268]; // [rsp+E0h] [rbp-20h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v23, 0x5Eu, "CVdsVolume::FormatPartitionEx2()");
  memset_0(v24, 0, sizeof(v24));
  memset_0(v25, 0, 0x208u);
  v20 = 0;
  v21 = 0;
  v12 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v20);
  if ( v12 >= 0 )
  {
    EnterCriticalSection(&g_GlobalCriticalSection);
    if ( a8 )
    {
      v13 = (CVdsDiskLun *)((char *)this - 72);
      *a8 = 0;
      v14 = CVdsDiskLun::ValidateDiskInterfaces(v13);
      v12 = v14;
      if ( v14 >= 0 )
      {
        v16 = CVdsDiskLun::BuildOEMPartitionName(v13, a2, v15, v24);
        v12 = v16;
        if ( v16 >= 0 )
        {
          v17 = AssignTempVolumeName(v24, v25);
          v12 = v17;
          if ( v17 >= 0 )
          {
            (*(void (__fastcall **)(CVdsDiskLun *))(*(_QWORD *)v13 + 8LL))(v13);
            v22 = GUID_NULL;
            v18 = CVdsVolume::FormatInternal(0, 0, &v22, v25, 1u, v24, a3, a4, a5, a6, a7, a8);
            v12 = v18;
            if ( v18 >= 0 )
            {
LABEL_14:
              LeaveCriticalSection(&g_GlobalCriticalSection);
              goto LABEL_15;
            }
            VdsTraceW(0, L"CVdsDiskLun::FormatPartitionEx2, 5, name=%s, hr=%lX", v24, (unsigned int)v18);
            (*(void (__fastcall **)(CVdsDiskLun *))(*(_QWORD *)v13 + 16LL))(v13);
          }
          else
          {
            VdsTraceW(0, L"CVdsDiskLun::FormatPartitionEx2, 4, name=%s, hr=%lX", v24, (unsigned int)v17);
          }
        }
        else
        {
          VdsTraceW(0, L"CVdsDiskLun::FormatPartitionEx2, 3, hr=%lX", (unsigned int)v16);
        }
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsDiskLun::FormatPartitionEx2, 2, hr=%lX", v14);
        if ( v12 == -2147212283 )
          v12 = -2147212277;
      }
    }
    else
    {
      v12 = -2147024809;
      VdsTraceEx(94, 0, "CVdsDiskLun::FormatPartitionEx2, 1, hr=%lX", -2147024809);
    }
    RemoveTempVolumeName(v25);
    goto LABEL_14;
  }
LABEL_15:
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v20);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140045df0  push    rbp
0x140045df2  push    rbx
0x140045df3  push    rsi
0x140045df4  push    rdi
0x140045df5  push    r12
0x140045df7  push    r13
0x140045df9  push    r14
0x140045dfb  push    r15
0x140045dfd  lea     rbp, [rsp-208h]
0x140045e05  sub     rsp, 308h
0x140045e0c  mov     rax, cs:__security_cookie
0x140045e13  xor     rax, rsp
0x140045e16  mov     [rbp+240h+var_48], rax
0x140045e1d  movzx   r12d, r9w
0x140045e21  mov     r15, r8
0x140045e24  mov     r14, rdx
0x140045e27  mov     rdi, rcx
0x140045e2a  mov     r13, [rbp+240h+arg_28]
0x140045e31  mov     rsi, [rbp+240h+arg_38]
0x140045e38  lea     r8, aCvdsvolumeForm_17; "CVdsVolume::FormatPartitionEx2()"
0x140045e3f  mov     edx, 5Eh ; '^'
0x140045e44  lea     rcx, [rbp+240h+var_2C0]
0x140045e48  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140045e4e  nop
0x140045e4f  xor     edx, edx; Val
0x140045e51  lea     r8d, [rdx+50h]; Size
0x140045e55  lea     rcx, [rbp+240h+var_2B0]; void *
0x140045e59  call    memset_0
0x140045e5e  xor     edx, edx; Val
0x140045e60  mov     r8d, 208h; Size
0x140045e66  lea     rcx, [rbp+240h+var_260]; void *
0x140045e6a  call    memset_0
0x140045e6f  xor     eax, eax
0x140045e71  mov     [rsp+340h+var_2E0], rax
0x140045e76  mov     [rsp+340h+var_2D8], eax
0x140045e7a  lea     rcx, [rsp+340h+var_2E0]; this
0x140045e7f  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140045e84  mov     ebx, eax
0x140045e86  test    eax, eax
0x140045e88  js      loc_14004600F
0x140045e8e  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140045e95  call    cs:__imp_EnterCriticalSection
0x140045e9b  nop
0x140045e9c  test    rsi, rsi
0x140045e9f  jnz     short loc_140045EC0
0x140045ea1  mov     ebx, 80070057h
0x140045ea6  mov     r9d, ebx
0x140045ea9  lea     r8, aCvdsdisklunFor_4; "CVdsDiskLun::FormatPartitionEx2, 1, hr="...
0x140045eb0  xor     edx, edx
0x140045eb2  lea     ecx, [rsi+5Eh]
0x140045eb5  call    cs:__imp_VdsTraceEx
0x140045ebb  jmp     loc_140045FF2
0x140045ec0  add     rdi, 0FFFFFFFFFFFFFFB8h
0x140045ec4  mov     qword ptr [rsi], 0
0x140045ecb  mov     rcx, rdi; this
0x140045ece  call    ?ValidateDiskInterfaces@CVdsDiskLun@@AEAAJXZ; CVdsDiskLun::ValidateDiskInterfaces(void)
0x140045ed3  mov     ebx, eax
0x140045ed5  test    eax, eax
0x140045ed7  jns     short loc_140045F04
0x140045ed9  mov     r9d, eax
0x140045edc  lea     r8, aCvdsdisklunFor_2; "CVdsDiskLun::FormatPartitionEx2, 2, hr="...
0x140045ee3  xor     edx, edx
0x140045ee5  lea     ecx, [rdx+5Eh]
0x140045ee8  call    cs:__imp_VdsTraceEx
0x140045eee  cmp     ebx, 80042405h
0x140045ef4  jnz     loc_140045FF2
0x140045efa  mov     ebx, 8004240Bh
0x140045eff  jmp     loc_140045FF2
0x140045f04  lea     r9, [rbp+240h+var_2B0]; unsigned __int16 *
0x140045f08  mov     rdx, r14; unsigned __int64
0x140045f0b  mov     rcx, rdi; this
0x140045f0e  call    ?BuildOEMPartitionName@CVdsDiskLun@@AEAAJ_KKPEAG@Z; CVdsDiskLun::BuildOEMPartitionName(unsigned __int64,ulong,ushort *)
0x140045f13  mov     ebx, eax
0x140045f15  test    eax, eax
0x140045f17  jns     short loc_140045F30
0x140045f19  mov     r8d, eax
0x140045f1c  lea     rdx, aCvdsdisklunFor_3; "CVdsDiskLun::FormatPartitionEx2, 3, hr="...
0x140045f23  xor     ecx, ecx
0x140045f25  call    cs:__imp_VdsTraceW
0x140045f2b  jmp     loc_140045FF2
0x140045f30  lea     rdx, [rbp+240h+var_260]
0x140045f34  lea     rcx, [rbp+240h+var_2B0]
0x140045f38  call    cs:__imp_AssignTempVolumeName
0x140045f3e  mov     ebx, eax
0x140045f40  test    eax, eax
0x140045f42  jns     short loc_140045F5F
0x140045f44  mov     r9d, eax
0x140045f47  lea     r8, [rbp+240h+var_2B0]
0x140045f4b  lea     rdx, aCvdsdisklunFor; "CVdsDiskLun::FormatPartitionEx2, 4, nam"...
0x140045f52  xor     ecx, ecx
0x140045f54  call    cs:__imp_VdsTraceW
0x140045f5a  jmp     loc_140045FF2
0x140045f5f  mov     rax, [rdi]
0x140045f62  mov     rcx, rdi
0x140045f65  mov     rax, [rax+8]
0x140045f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045f6e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140045f75  movdqu  xmmword ptr [rsp+340h+var_2D0.Data1], xmm0
0x140045f7b  mov     [rsp+340h+var_2E8], rsi; struct IVdsAsync **
0x140045f80  mov     eax, dword ptr [rbp+240h+arg_30]
0x140045f86  mov     [rsp+340h+var_2F0], eax; unsigned int
0x140045f8a  mov     [rsp+340h+var_2F8], r13; unsigned __int16 *
0x140045f8f  mov     eax, [rbp+240h+arg_20]
0x140045f95  mov     [rsp+340h+var_300], eax; unsigned int
0x140045f99  mov     [rsp+340h+var_308], r12w; unsigned __int16
0x140045f9f  mov     [rsp+340h+String1], r15; String1
0x140045fa4  lea     rax, [rbp+240h+var_2B0]
0x140045fa8  mov     [rsp+340h+var_318], rax; unsigned __int16 *
0x140045fad  mov     [rsp+340h+var_320], 1; int
0x140045fb5  lea     r9, [rbp+240h+var_260]; unsigned __int16 *
0x140045fb9  lea     r8, [rsp+340h+var_2D0]; struct _GUID *
0x140045fbe  xor     edx, edx; unsigned int *
0x140045fc0  xor     ecx, ecx; struct CVdsVolume *
0x140045fc2  call    ?FormatInternal@CVdsVolume@@SAJPEAV1@PEAKU_GUID@@PEAGH33GK3KPEAPEAUIVdsAsync@@@Z; CVdsVolume::FormatInternal(CVdsVolume *,ulong *,_GUID,ushort *,int,ushort *,ushort *,ushort,ulong,ushort *,ulong,IVdsAsync * *)
0x140045fc7  mov     ebx, eax
0x140045fc9  test    eax, eax
0x140045fcb  jns     short loc_140046001
0x140045fcd  mov     r9d, eax
0x140045fd0  lea     r8, [rbp+240h+var_2B0]
0x140045fd4  lea     rdx, aCvdsdisklunFor_6; "CVdsDiskLun::FormatPartitionEx2, 5, nam"...
0x140045fdb  xor     ecx, ecx
0x140045fdd  call    cs:__imp_VdsTraceW
0x140045fe3  mov     rax, [rdi]
0x140045fe6  mov     rcx, rdi
0x140045fe9  mov     rax, [rax+10h]
0x140045fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045ff2  lea     rdx, [rbp+240h+var_2B0]
0x140045ff6  lea     rcx, [rbp+240h+var_260]
0x140045ffa  call    cs:__imp_RemoveTempVolumeName
0x140046000  nop
0x140046001  lea     rcx, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140046008  call    cs:__imp_LeaveCriticalSection
0x14004600e  nop
0x14004600f  lea     rcx, [rsp+340h+var_2E0]; this
0x140046014  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140046019  nop
0x14004601a  lea     rcx, [rbp+240h+var_2C0]
0x14004601e  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140046024  mov     eax, ebx
0x140046026  mov     rcx, [rbp+240h+var_48]
0x14004602d  xor     rcx, rsp; StackCookie
0x140046030  call    __security_check_cookie
0x140046035  add     rsp, 308h
0x14004603c  pop     r15
0x14004603e  pop     r14
0x140046040  pop     r13
0x140046042  pop     r12
0x140046044  pop     rdi
0x140046045  pop     rsi
0x140046046  pop     rbx
0x140046047  pop     rbp
0x140046048  retn
```
