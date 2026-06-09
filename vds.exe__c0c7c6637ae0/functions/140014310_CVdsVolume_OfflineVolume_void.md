# CVdsVolume::OfflineVolume(void)

- ea: `0x140014310`
- end: `0x140014528`
- name: `?OfflineVolume@CVdsVolume@@UEAAJXZ`
- size: `536`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000d0f0`
- `0x140013298`
- `0x140014310`
- `0x140044170`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400144eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400144eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400144b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400144b3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400144a9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400144a9`
- `vdsutil!OpenDevice` at `0x140014420`
- `vdsutil!OpenDevice` at `0x140014420`
- `vdsutil!VdsTraceEx` at `0x1400143bb`
- `vdsutil!VdsTraceEx` at `0x1400144dc`
- `vdsutil!VdsTraceEx` at `0x1400143bb`
- `vdsutil!VdsTraceEx` at `0x1400144dc`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001436b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001436b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400144fd`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400144fd`
- `vdsutil!VdsTraceW` at `0x140014391`
- `vdsutil!VdsTraceW` at `0x140014391`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsVolume::OfflineVolume(CVdsVolume *this)
{
  unsigned int v2; // ebx
  int v3; // eax
  const char *v4; // r8
  signed int v5; // eax
  signed int LastError; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-29h] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v10[16]; // [rsp+50h] [rbp-19h] BYREF
  int v11; // [rsp+60h] [rbp-9h] BYREF
  __int128 v12; // [rsp+64h] [rbp-5h]
  __int128 v13; // [rsp+74h] [rbp+Bh]
  _BYTE pv[20]; // [rsp+84h] [rbp+1Bh] BYREF

  v11 = 0;
  v12 = 0;
  v13 = 0;
  memset(pv, 0, sizeof(pv));
  hDevice = (HANDLE)-1LL;
  BytesReturned = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v10, 0x5Eu, "CVdsVolume::OfflineVolume()");
  if ( !*((_QWORD *)this + 11) )
  {
    v2 = -2147211946;
    VdsTraceW(0, L"CVdsVolume::OfflineVolume, 0, hr=%lX", 2147755350LL);
    goto LABEL_24;
  }
  v3 = CVdsVolume::ValidateCall((CVdsVolume *)((char *)this - 40), 7u);
  v2 = v3;
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 11) + 24LL))(*((_QWORD *)this + 11), &v11);
    v2 = v3;
    if ( v3 >= 0 )
    {
      if ( (*(_DWORD *)&pv[4] & 0x40000) != 0 )
      {
        v2 = 0;
      }
      else if ( (*(_DWORD *)&pv[4] & 0x80000) != 0 )
      {
        v5 = OpenDevice(*(_QWORD *)&pv[12], 3221225472LL, &hDevice);
        if ( v5 )
        {
          if ( v5 > 0 )
            v2 = (unsigned __int16)v5 | 0x80070000;
          else
            v2 = v5;
          VdsLogError(0xC2000008, 0, 0, v5, 0x20A001Cu, *(unsigned __int16 **)&pv[12], 0);
          VdsTraceEx(94, 0, "CVdsVolume::OfflineVolume failed, 3, hr=%lX", v2);
        }
        else if ( !DeviceIoControl(hDevice, 0x56C00Cu, 0, 0, 0, 0, &BytesReturned, 0) )
        {
          LastError = GetLastError();
          v2 = LastError;
          if ( LastError > 0 )
            v2 = (unsigned __int16)LastError | 0x80070000;
          VdsTraceEx(
            94,
            0,
            "CVdsVolume::OfflineVolume: IOCTL_VOLUME_OFFLINE(%S) failed, 4, hr=%lX",
            *(const wchar_t **)&pv[12],
            v2);
        }
      }
      else
      {
        v2 = -2147210970;
        VdsTraceEx(94, 0, "CVdsVolume::OfflineVolume failed, 2, hr=%lX", 2147756326LL);
      }
      goto LABEL_22;
    }
    v4 = "CVdsVolume::OfflineVolume failed, 1, hr=%lX";
  }
  else
  {
    v4 = "CVdsVolume::OfflineVolume, .5, hr=%lX";
  }
  VdsTraceEx(94, 0, v4, (unsigned int)v3);
LABEL_22:
  if ( *(_QWORD *)&pv[12] )
  {
    CoTaskMemFree(*(LPVOID *)&pv[12]);
    *(_QWORD *)&pv[12] = 0;
  }
LABEL_24:
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v10);
  CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&hDevice);
  return v2;
}

```

## disassembly

```asm
0x140014310  push    rbp
0x140014312  push    rbx
0x140014313  push    rdi
0x140014314  push    r14
0x140014316  lea     rbp, [rsp-3Fh]
0x14001431b  sub     rsp, 0A8h
0x140014322  mov     rax, cs:__security_cookie
0x140014329  xor     rax, rsp
0x14001432c  mov     [rbp+57h+var_28], rax
0x140014330  mov     rdi, rcx
0x140014333  mov     [rbp+57h+var_60], 0
0x14001433a  xorps   xmm0, xmm0
0x14001433d  xor     eax, eax
0x14001433f  movups  [rbp+57h+var_5C], xmm0
0x140014343  movups  [rbp+57h+var_4C], xmm0
0x140014347  movups  xmmword ptr [rbp+57h+pv], xmm0
0x14001434b  mov     [rbp+57h+var_2C], eax
0x14001434e  mov     [rbp+57h+hDevice], 0FFFFFFFFFFFFFFFFh
0x140014356  mov     [rbp+57h+BytesReturned], eax
0x140014359  lea     r8, aCvdsvolumeOffl_3; "CVdsVolume::OfflineVolume()"
0x140014360  lea     r14d, [rax+5Eh]
0x140014364  mov     edx, r14d
0x140014367  lea     rcx, [rbp+57h+var_70]
0x14001436b  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140014371  nop
0x140014372  lea     rcx, [rdi-28h]; this
0x140014376  cmp     qword ptr [rcx+80h], 0
0x14001437e  jnz     short loc_14001439C
0x140014380  mov     ebx, 80042556h
0x140014385  mov     r8d, ebx
0x140014388  lea     rdx, aCvdsvolumeOffl_4; "CVdsVolume::OfflineVolume, 0, hr=%lX"
0x14001438f  xor     ecx, ecx
0x140014391  call    cs:__imp_VdsTraceW
0x140014397  jmp     loc_1400144F9
0x14001439c  mov     edx, 7; unsigned int
0x1400143a1  call    ?ValidateCall@CVdsVolume@@AEAAJK@Z; CVdsVolume::ValidateCall(ulong)
0x1400143a6  mov     ebx, eax
0x1400143a8  test    eax, eax
0x1400143aa  jns     short loc_1400143C6
0x1400143ac  lea     r8, aCvdsvolumeOffl_2; "CVdsVolume::OfflineVolume, .5, hr=%lX"
0x1400143b3  mov     r9d, eax
0x1400143b6  xor     edx, edx
0x1400143b8  mov     ecx, r14d
0x1400143bb  call    cs:__imp_VdsTraceEx
0x1400143c1  jmp     loc_1400144E2
0x1400143c6  mov     rcx, [rdi+58h]
0x1400143ca  mov     rax, [rcx]
0x1400143cd  lea     rdx, [rbp+57h+var_60]
0x1400143d1  mov     rax, [rax+18h]
0x1400143d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400143da  mov     ebx, eax
0x1400143dc  test    eax, eax
0x1400143de  jns     short loc_1400143E9
0x1400143e0  lea     r8, aCvdsvolumeOffl; "CVdsVolume::OfflineVolume failed, 1, hr"...
0x1400143e7  jmp     short loc_1400143B3
0x1400143e9  test    dword ptr [rbp+57h+pv+4], 40000h
0x1400143f0  jz      short loc_1400143F9
0x1400143f2  xor     ebx, ebx
0x1400143f4  jmp     loc_1400144E2
0x1400143f9  test    dword ptr [rbp+57h+pv+4], 80000h
0x140014400  jnz     short loc_140014413
0x140014402  mov     ebx, 80042926h
0x140014407  mov     r9d, ebx
0x14001440a  lea     r8, aCvdsvolumeOffl_1; "CVdsVolume::OfflineVolume failed, 2, hr"...
0x140014411  jmp     short loc_1400143B6
0x140014413  lea     r8, [rbp+57h+hDevice]
0x140014417  mov     edx, 0C0000000h
0x14001441c  mov     rcx, [rbp+57h+pv+0Ch]
0x140014420  call    cs:__imp_OpenDevice
0x140014426  mov     r9d, eax; unsigned int
0x140014429  test    eax, eax
0x14001442b  jz      short loc_140014477
0x14001442d  test    eax, eax
0x14001442f  jg      short loc_140014435
0x140014431  mov     ebx, eax
0x140014433  jmp     short loc_14001443F
0x140014435  movzx   ebx, r9w
0x140014439  or      ebx, 80070000h
0x14001443f  mov     [rsp+0C0h+lpBytesReturned], 0
0x140014448  mov     rax, [rbp+57h+pv+0Ch]
0x14001444c  mov     qword ptr [rsp+0C0h+nOutBufferSize], rax; unsigned __int16 *
0x140014451  mov     dword ptr [rsp+0C0h+lpOutBuffer], 20A001Ch; unsigned int
0x140014459  xor     r8d, r8d; void *
0x14001445c  xor     edx, edx; unsigned int
0x14001445e  mov     ecx, 0C2000008h; unsigned int
0x140014463  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140014468  mov     r9d, ebx
0x14001446b  lea     r8, aCvdsvolumeOffl_0; "CVdsVolume::OfflineVolume failed, 3, hr"...
0x140014472  jmp     loc_1400143B6
0x140014477  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x140014480  lea     rax, [rbp+57h+BytesReturned]
0x140014484  mov     [rsp+0C0h+lpBytesReturned], rax; lpBytesReturned
0x140014489  mov     [rsp+0C0h+nOutBufferSize], 0; nOutBufferSize
0x140014491  mov     [rsp+0C0h+lpOutBuffer], 0; lpOutBuffer
0x14001449a  xor     r9d, r9d; nInBufferSize
0x14001449d  xor     r8d, r8d; lpInBuffer
0x1400144a0  mov     edx, 56C00Ch; dwIoControlCode
0x1400144a5  mov     rcx, [rbp+57h+hDevice]; hDevice
0x1400144a9  call    cs:__imp_DeviceIoControl
0x1400144af  test    eax, eax
0x1400144b1  jnz     short loc_1400144E2
0x1400144b3  call    cs:__imp_GetLastError
0x1400144b9  mov     ebx, eax
0x1400144bb  test    eax, eax
0x1400144bd  jle     short loc_1400144C8
0x1400144bf  movzx   ebx, ax
0x1400144c2  or      ebx, 80070000h
0x1400144c8  mov     dword ptr [rsp+0C0h+lpOutBuffer], ebx
0x1400144cc  mov     r9, [rbp+57h+pv+0Ch]
0x1400144d0  lea     r8, aCvdsvolumeOffl_5; "CVdsVolume::OfflineVolume: IOCTL_VOLUME"...
0x1400144d7  xor     edx, edx
0x1400144d9  mov     ecx, r14d
0x1400144dc  call    cs:__imp_VdsTraceEx
0x1400144e2  mov     rcx, [rbp+57h+pv+0Ch]; pv
0x1400144e6  test    rcx, rcx
0x1400144e9  jz      short loc_1400144F9
0x1400144eb  call    cs:__imp_CoTaskMemFree
0x1400144f1  mov     [rbp+57h+pv+0Ch], 0
0x1400144f9  lea     rcx, [rbp+57h+var_70]
0x1400144fd  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140014503  nop
0x140014504  lea     rcx, [rbp+57h+hDevice]
0x140014508  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x14001450d  mov     eax, ebx
0x14001450f  mov     rcx, [rbp+57h+var_28]
0x140014513  xor     rcx, rsp; StackCookie
0x140014516  call    __security_check_cookie
0x14001451b  add     rsp, 0A8h
0x140014522  pop     r14
0x140014524  pop     rdi
0x140014525  pop     rbx
0x140014526  pop     rbp
0x140014527  retn
```
