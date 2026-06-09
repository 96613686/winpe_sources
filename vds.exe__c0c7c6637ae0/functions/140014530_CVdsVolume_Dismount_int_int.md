# CVdsVolume::Dismount(int,int)

- ea: `0x140014530`
- end: `0x14001483c`
- name: `?Dismount@CVdsVolume@@UEAAJHH@Z`
- size: `780`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x14000d0f0`
- `0x14000e270`
- `0x140013298`
- `0x140014530`
- `0x140044170`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147b3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400147a9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400147a9`
- `vdsutil!OpenDevice` at `0x14001465e`
- `vdsutil!OpenDevice` at `0x14001465e`
- `vdsutil!LockDismountVolume` at `0x14001472d`
- `vdsutil!LockDismountVolume` at `0x14001472d`
- `vdsutil!CoFreeStringArray` at `0x14001471d`
- `vdsutil!CoFreeStringArray` at `0x14001471d`
- `vdsutil!VdsTraceEx` at `0x1400145e1`
- `vdsutil!VdsTraceEx` at `0x1400146b9`
- `vdsutil!VdsTraceEx` at `0x1400147cf`
- `vdsutil!VdsTraceEx` at `0x1400145e1`
- `vdsutil!VdsTraceEx` at `0x1400146b9`
- `vdsutil!VdsTraceEx` at `0x1400147cf`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001459c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001459c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400147fd`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400147fd`

## string_xrefs

- `0x140014766`: `CVdsVolume::Dismount, 10, hr=%lX`
- `0x1400146ad`: `CVdsVolume::Dismount, 6, hr=%lX`
- `0x1400147c3`: `CVdsVolume::Dismount: IOCTL_VOLUME_OFFLINE(%S) failed: %X`
- `0x14001458a`: `CVdsVolume::Dismount()`
- `0x1400145ba`: `CVdsVolume::Dismount, 1, hr=%lX`
- `0x1400145d2`: `CVdsVolume::Dismount, 2, hr=%lX`
- `0x140014609`: `CVdsVolume::Dismount, 3, hr=%lX`
- `0x14001462c`: `CVdsVolume::Dismount, 4, hr=%lX`
- `0x14001464c`: `CVdsVolume::Dismount, 5, hr=%lX`
- `0x1400146f4`: `CVdsVolume::Dismount, 7, hr=%lX`
- `0x14001470b`: `CVdsVolume::Dismount, 8, hr=%lX`
- `0x140014743`: `CVdsVolume::Dismount, 9, hr=%lX`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsVolume::Dismount(CVdsVolume *this, unsigned int a2, int a3)
{
  int v6; // eax
  signed int LastError; // ebx
  const char *v8; // r8
  int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // r8
  int v12; // esi
  __int64 v13; // r9
  int v14; // eax
  int v15; // eax
  __int64 v16; // r9
  HANDLE v17; // rax
  HANDLE hDevice; // [rsp+40h] [rbp-39h] BYREF
  int v20; // [rsp+48h] [rbp-31h] BYREF
  DWORD BytesReturned; // [rsp+4Ch] [rbp-2Dh] BYREF
  __int64 v22; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int16 *v23; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v24[16]; // [rsp+60h] [rbp-19h] BYREF
  _OWORD v25[2]; // [rsp+70h] [rbp-9h] BYREF
  __int128 v26; // [rsp+90h] [rbp+17h]
  unsigned __int16 *v27; // [rsp+A0h] [rbp+27h]

  memset(v25, 0, sizeof(v25));
  v26 = 0;
  v27 = 0;
  v23 = 0;
  hDevice = (HANDLE)-1LL;
  BytesReturned = 0;
  v22 = 0;
  v20 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v24, 0x5Eu, "CVdsVolume::Dismount()");
  v6 = CVdsVolume::ValidateCall((CVdsVolume *)((char *)this - 24), 0xCu);
  LastError = v6;
  if ( v6 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::Dismount, 1, hr=%lX", (unsigned int)v6);
    goto LABEL_41;
  }
  if ( *((_QWORD *)this + 17) != -1 )
  {
    LastError = -2147212196;
    v8 = "CVdsVolume::Dismount, 2, hr=%lX";
LABEL_5:
    VdsTraceEx(94, 0, v8, (unsigned int)LastError);
    goto LABEL_41;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13), v25);
  LastError = v9;
  if ( v9 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::Dismount, 3, hr=%lX", (unsigned int)v9);
    goto LABEL_41;
  }
  v23 = v27;
  if ( (DWORD2(v26) & 0x80000) == 0 && a3 )
  {
    LastError = -2147212288;
    v8 = "CVdsVolume::Dismount, 4, hr=%lX";
    goto LABEL_5;
  }
  if ( (DWORD2(v26) & 0x40000) != 0 )
  {
    if ( a3 != 1 )
    {
      LastError = -2147212195;
      v8 = "CVdsVolume::Dismount, 5, hr=%lX";
      goto LABEL_5;
    }
    goto LABEL_40;
  }
  v10 = OpenDevice(v27, 3221225472LL, &hDevice);
  LastError = v10;
  if ( v10 )
  {
    VdsLogError(0xC2000008, 0, 0, v10, 0x20A0019u, v27, 0);
    v12 = (unsigned __int16)LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    else
      v13 = (unsigned int)LastError;
    VdsTraceEx(94, 0, "CVdsVolume::Dismount, 6, hr=%lX", v13);
LABEL_20:
    if ( LastError > 0 )
      LastError = v12 | 0x80070000;
    goto LABEL_41;
  }
  if ( a3 )
  {
    v14 = (*(__int64 (__fastcall **)(CVdsVolume *, __int64 *, int *))(*(_QWORD *)this + 48LL))(this, &v22, &v20);
    LastError = v14;
    if ( v14 < 0 )
    {
      VdsTraceEx(94, 0, "CVdsVolume::Dismount, 7, hr=%lX", (unsigned int)v14);
      goto LABEL_41;
    }
    if ( v20 )
    {
      LastError = -2147212194;
      v8 = "CVdsVolume::Dismount, 8, hr=%lX";
      goto LABEL_5;
    }
    CoFreeStringArray(v22, 0);
  }
  LOBYTE(v11) = 1;
  v15 = LockDismountVolume(hDevice, a2, v11);
  LastError = v15;
  if ( v15 )
  {
    if ( v15 == 5 )
    {
      LastError = -2147212269;
      v8 = "CVdsVolume::Dismount, 9, hr=%lX";
      goto LABEL_5;
    }
    v12 = (unsigned __int16)v15;
    if ( v15 > 0 )
      v16 = (unsigned __int16)v15 | 0x80070000;
    else
      v16 = (unsigned int)v15;
    VdsTraceEx(94, 0, "CVdsVolume::Dismount, 10, hr=%lX", v16);
    goto LABEL_20;
  }
  if ( a3 != 1 )
  {
    v17 = hDevice;
    hDevice = (HANDLE)-1LL;
    *((_QWORD *)this + 17) = v17;
    goto LABEL_40;
  }
  if ( DeviceIoControl(hDevice, 0x56C00Cu, 0, 0, 0, 0, &BytesReturned, 0) )
  {
LABEL_40:
    LastError = 0;
    goto LABEL_41;
  }
  LastError = GetLastError();
  VdsTraceEx(94, 0, "CVdsVolume::Dismount: IOCTL_VOLUME_OFFLINE(%S) failed: %X", v27, LastError);
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_41:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v24);
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&hDevice);
  CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>((void **)&v23);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140014530  mov     [rsp-8+arg_10], rbx
0x140014535  push    rbp
0x140014536  push    rsi
0x140014537  push    rdi
0x140014538  push    r12
0x14001453a  push    r14
0x14001453c  lea     rbp, [rsp-37h]
0x140014541  sub     rsp, 0B0h
0x140014548  mov     rax, cs:__security_cookie
0x14001454f  xor     rax, rsp
0x140014552  mov     [rbp+57h+var_28], rax
0x140014556  mov     edi, r8d
0x140014559  mov     r14d, edx
0x14001455c  mov     rsi, rcx
0x14001455f  xorps   xmm0, xmm0
0x140014562  xor     eax, eax
0x140014564  movups  [rbp+57h+var_60], xmm0
0x140014568  movups  [rbp+57h+var_50], xmm0
0x14001456c  movups  [rbp+57h+var_40], xmm0
0x140014570  mov     [rbp+57h+var_30], rax
0x140014574  mov     [rbp+57h+var_78], rax
0x140014578  mov     [rbp+57h+hDevice], 0FFFFFFFFFFFFFFFFh
0x140014580  mov     [rbp+57h+BytesReturned], eax
0x140014583  mov     [rbp+57h+var_80], rax
0x140014587  mov     [rbp+57h+var_88], eax
0x14001458a  lea     r8, aCvdsvolumeDism_0; "CVdsVolume::Dismount()"
0x140014591  lea     r12d, [rax+5Eh]
0x140014595  mov     edx, r12d
0x140014598  lea     rcx, [rbp+57h+var_70]
0x14001459c  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400145a2  nop
0x1400145a3  lea     rcx, [rsi-18h]; this
0x1400145a7  lea     edx, [r12-52h]; unsigned int
0x1400145ac  call    ?ValidateCall@CVdsVolume@@AEAAJK@Z; CVdsVolume::ValidateCall(ulong)
0x1400145b1  mov     ebx, eax
0x1400145b3  test    eax, eax
0x1400145b5  jns     short loc_1400145C3
0x1400145b7  mov     r9d, eax
0x1400145ba  lea     r8, aCvdsvolumeDism_9; "CVdsVolume::Dismount, 1, hr=%lX"
0x1400145c1  jmp     short loc_1400145DC
0x1400145c3  cmp     qword ptr [rsi+88h], 0FFFFFFFFFFFFFFFFh
0x1400145cb  jz      short loc_1400145EC
0x1400145cd  mov     ebx, 8004245Ch
0x1400145d2  lea     r8, aCvdsvolumeDism_3; "CVdsVolume::Dismount, 2, hr=%lX"
0x1400145d9  mov     r9d, ebx
0x1400145dc  xor     edx, edx
0x1400145de  mov     ecx, r12d
0x1400145e1  call    cs:__imp_VdsTraceEx
0x1400145e7  jmp     loc_1400147F9
0x1400145ec  mov     rcx, [rsi+68h]
0x1400145f0  mov     rax, [rcx]
0x1400145f3  lea     rdx, [rbp+57h+var_60]
0x1400145f7  mov     rax, [rax+18h]
0x1400145fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014600  mov     ebx, eax
0x140014602  test    eax, eax
0x140014604  jns     short loc_140014612
0x140014606  mov     r9d, eax
0x140014609  lea     r8, aCvdsvolumeDism; "CVdsVolume::Dismount, 3, hr=%lX"
0x140014610  jmp     short loc_1400145DC
0x140014612  mov     rcx, [rbp+57h+var_30]
0x140014616  mov     [rbp+57h+var_78], rcx
0x14001461a  test    dword ptr [rbp+57h+var_40+8], 80000h
0x140014621  jnz     short loc_140014635
0x140014623  test    edi, edi
0x140014625  jz      short loc_140014635
0x140014627  mov     ebx, 80042400h
0x14001462c  lea     r8, aCvdsvolumeDism_8; "CVdsVolume::Dismount, 4, hr=%lX"
0x140014633  jmp     short loc_1400145D9
0x140014635  test    dword ptr [rbp+57h+var_40+8], 40000h
0x14001463c  jz      short loc_140014655
0x14001463e  cmp     edi, 1
0x140014641  jz      loc_1400147F7
0x140014647  mov     ebx, 8004245Dh
0x14001464c  lea     r8, aCvdsvolumeDism_10; "CVdsVolume::Dismount, 5, hr=%lX"
0x140014653  jmp     short loc_1400145D9
0x140014655  lea     r8, [rbp+57h+hDevice]
0x140014659  mov     edx, 0C0000000h
0x14001465e  call    cs:__imp_OpenDevice
0x140014664  mov     ebx, eax
0x140014666  test    eax, eax
0x140014668  jz      short loc_1400146D0
0x14001466a  mov     [rsp+0D0h+lpBytesReturned], 0
0x140014673  mov     rcx, [rbp+57h+var_30]
0x140014677  mov     qword ptr [rsp+0D0h+nOutBufferSize], rcx; unsigned __int16 *
0x14001467c  mov     dword ptr [rsp+0D0h+lpOutBuffer], 20A0019h; unsigned int
0x140014684  mov     r9d, eax; unsigned int
0x140014687  xor     r8d, r8d; void *
0x14001468a  xor     edx, edx; unsigned int
0x14001468c  mov     ecx, 0C2000008h; unsigned int
0x140014691  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140014696  movzx   esi, bx
0x140014699  mov     edi, 80070000h
0x14001469e  test    ebx, ebx
0x1400146a0  jg      short loc_1400146A7
0x1400146a2  mov     r9d, ebx
0x1400146a5  jmp     short loc_1400146AD
0x1400146a7  mov     r9d, esi
0x1400146aa  or      r9d, edi
0x1400146ad  lea     r8, aCvdsvolumeDism_1; "CVdsVolume::Dismount, 6, hr=%lX"
0x1400146b4  xor     edx, edx
0x1400146b6  mov     ecx, r12d
0x1400146b9  call    cs:__imp_VdsTraceEx
0x1400146bf  test    ebx, ebx
0x1400146c1  jle     loc_1400147F9
0x1400146c7  mov     ebx, esi
0x1400146c9  or      ebx, edi
0x1400146cb  jmp     loc_1400147F9
0x1400146d0  test    edi, edi
0x1400146d2  jz      short loc_140014723
0x1400146d4  mov     rax, [rsi]
0x1400146d7  lea     r8, [rbp+57h+var_88]
0x1400146db  lea     rdx, [rbp+57h+var_80]
0x1400146df  mov     rcx, rsi
0x1400146e2  mov     rax, [rax+30h]
0x1400146e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400146eb  mov     ebx, eax
0x1400146ed  test    eax, eax
0x1400146ef  jns     short loc_140014700
0x1400146f1  mov     r9d, eax
0x1400146f4  lea     r8, aCvdsvolumeDism_6; "CVdsVolume::Dismount, 7, hr=%lX"
0x1400146fb  jmp     loc_1400145DC
0x140014700  cmp     [rbp+57h+var_88], 0
0x140014704  jz      short loc_140014717
0x140014706  mov     ebx, 8004245Eh
0x14001470b  lea     r8, aCvdsvolumeDism_4; "CVdsVolume::Dismount, 8, hr=%lX"
0x140014712  jmp     loc_1400145D9
0x140014717  xor     edx, edx
0x140014719  mov     rcx, [rbp+57h+var_80]
0x14001471d  call    cs:__imp_CoFreeStringArray
0x140014723  mov     r8b, 1
0x140014726  mov     edx, r14d
0x140014729  mov     rcx, [rbp+57h+hDevice]
0x14001472d  call    cs:__imp_LockDismountVolume
0x140014733  mov     ebx, eax
0x140014735  test    eax, eax
0x140014737  jz      short loc_140014772
0x140014739  cmp     eax, 5
0x14001473c  jnz     short loc_14001474F
0x14001473e  mov     ebx, 80042413h
0x140014743  lea     r8, aCvdsvolumeDism_5; "CVdsVolume::Dismount, 9, hr=%lX"
0x14001474a  jmp     loc_1400145D9
0x14001474f  movzx   esi, bx
0x140014752  mov     edi, 80070000h
0x140014757  test    ebx, ebx
0x140014759  jg      short loc_140014760
0x14001475b  mov     r9d, ebx
0x14001475e  jmp     short loc_140014766
0x140014760  mov     r9d, esi
0x140014763  or      r9d, edi
0x140014766  lea     r8, aCvdsvolumeDism_2; "CVdsVolume::Dismount, 10, hr=%lX"
0x14001476d  jmp     loc_1400146B4
0x140014772  cmp     edi, 1
0x140014775  jnz     short loc_1400147E4
0x140014777  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x140014780  lea     rax, [rbp+57h+BytesReturned]
0x140014784  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x140014789  mov     [rsp+0D0h+nOutBufferSize], 0; nOutBufferSize
0x140014791  mov     [rsp+0D0h+lpOutBuffer], 0; lpOutBuffer
0x14001479a  xor     r9d, r9d; nInBufferSize
0x14001479d  xor     r8d, r8d; lpInBuffer
0x1400147a0  mov     edx, 56C00Ch; dwIoControlCode
0x1400147a5  mov     rcx, [rbp+57h+hDevice]; hDevice
0x1400147a9  call    cs:__imp_DeviceIoControl
0x1400147af  test    eax, eax
0x1400147b1  jnz     short loc_1400147F7
0x1400147b3  call    cs:__imp_GetLastError
0x1400147b9  mov     ebx, eax
0x1400147bb  mov     dword ptr [rsp+0D0h+lpOutBuffer], eax
0x1400147bf  mov     r9, [rbp+57h+var_30]
0x1400147c3  lea     r8, aCvdsvolumeDism_7; "CVdsVolume::Dismount: IOCTL_VOLUME_OFFL"...
0x1400147ca  xor     edx, edx
0x1400147cc  mov     ecx, r12d
0x1400147cf  call    cs:__imp_VdsTraceEx
0x1400147d5  test    ebx, ebx
0x1400147d7  jle     short loc_1400147F9
0x1400147d9  movzx   ebx, bx
0x1400147dc  or      ebx, 80070000h
0x1400147e2  jmp     short loc_1400147F9
0x1400147e4  mov     rax, [rbp+57h+hDevice]
0x1400147e8  mov     [rbp+57h+hDevice], 0FFFFFFFFFFFFFFFFh
0x1400147f0  mov     [rsi+88h], rax
0x1400147f7  xor     ebx, ebx
0x1400147f9  lea     rcx, [rbp+57h+var_70]
0x1400147fd  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140014803  nop
0x140014804  lea     rcx, [rbp+57h+hDevice]
0x140014808  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14001480d  nop
0x14001480e  lea     rcx, [rbp+57h+var_78]
0x140014812  call    ??1?$CVdsCoTaskPtr@G@@QEAA@XZ; CVdsCoTaskPtr<ushort>::~CVdsCoTaskPtr<ushort>(void)
0x140014817  mov     eax, ebx
0x140014819  mov     rcx, [rbp+57h+var_28]
0x14001481d  xor     rcx, rsp; StackCookie
0x140014820  call    __security_check_cookie
0x140014825  mov     rbx, [rsp+0D0h+arg_10]
0x14001482d  add     rsp, 0B0h
0x140014834  pop     r14
0x140014836  pop     r12
0x140014838  pop     rdi
0x140014839  pop     rsi
0x14001483a  pop     rbp
0x14001483b  retn
```
