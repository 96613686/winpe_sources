# CVdsVolume::Mount(void)

- ea: `0x14001ffa0`
- end: `0x14002024b`
- name: `?Mount@CVdsVolume@@UEAAJXZ`
- size: `683`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x14000d0f0`
- `0x14000e270`
- `0x140013298`
- `0x14001ffa0`
- `0x1400427c4`
- `0x140044170`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020211`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020056`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140020207`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140020207`
- `vdsutil!OpenDevice` at `0x1400201b0`
- `vdsutil!OpenDevice` at `0x1400201b0`
- `vdsutil!MountVolume` at `0x14002008e`
- `vdsutil!MountVolume` at `0x14002023b`
- `vdsutil!MountVolume` at `0x14002008e`
- `vdsutil!MountVolume` at `0x14002023b`
- `vdsutil!VdsTraceEx` at `0x140020023`
- `vdsutil!VdsTraceEx` at `0x14002010a`
- `vdsutil!VdsTraceEx` at `0x140020228`
- `vdsutil!VdsTraceEx` at `0x140020023`
- `vdsutil!VdsTraceEx` at `0x14002010a`
- `vdsutil!VdsTraceEx` at `0x140020228`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001ffdf`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001ffdf`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140020038`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400200b0`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140020038`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400200b0`
- `vdsutil!VdsTraceW` at `0x140020158`
- `vdsutil!VdsTraceW` at `0x140020158`

## string_xrefs

- `0x14002021c`: `CVdsVolume::Mount, 4, %lX`
- `0x14001ffcb`: `CVdsVolume::Mount()`
- `0x140020017`: `CVdsVolume::Mount, .5, hr=%lX`
- `0x14002007d`: `CVdsVolume::Mount, 1, (%S) failed: %lX`
- `0x1400200f6`: `CVdsVolume::Mount, 2, (%S) failed: %lX`
- `0x14002014f`: `CVdsVolume::Mount, 3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CVdsVolume::Mount(CVdsVolume *this)
{
  CVdsVolume *v2; // rsi
  int v3; // eax
  unsigned int v4; // edi
  void *v6; // rcx
  int v7; // eax
  signed int LastError; // ebx
  const char *v9; // r8
  void *v10; // rcx
  signed int v11; // eax
  int IsPackOffline; // eax
  signed int v13; // eax
  bool v14; // cc
  HANDLE hDevice; // [rsp+40h] [rbp-29h] BYREF
  void *v16; // [rsp+48h] [rbp-21h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v18[16]; // [rsp+58h] [rbp-11h] BYREF
  __int128 v19; // [rsp+68h] [rbp-1h] BYREF
  __int128 v20; // [rsp+78h] [rbp+Fh]
  __int128 v21; // [rsp+88h] [rbp+1Fh]
  void *v22; // [rsp+98h] [rbp+2Fh]

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v18, 0x5Eu, "CVdsVolume::Mount()");
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v16 = 0;
  v2 = (CVdsVolume *)((char *)this - 24);
  v3 = CVdsVolume::ValidateCall((CVdsVolume *)((char *)this - 24), 0xBu);
  v4 = v3;
  if ( v3 < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::Mount, .5, hr=%lX", v3);
    CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>(&v16);
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
    return v4;
  }
  v6 = (void *)*((_QWORD *)this + 17);
  if ( v6 == (void *)-1LL )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13), &v19);
    LastError = v7;
    if ( v7 < 0 )
    {
      v9 = "CVdsVolume::Mount, 2, (%S) failed: %lX";
      goto LABEL_13;
    }
    v10 = v22;
    v16 = v22;
    if ( DWORD1(v20) == 5 )
    {
      LastError = -2147212239;
      goto LABEL_10;
    }
    if ( !v22 )
    {
      IsPackOffline = CVdsVolume::IsPackOffline(v2);
      LastError = IsPackOffline;
      if ( IsPackOffline >= 0 )
      {
        if ( IsPackOffline )
        {
          VdsTraceW(0, L"CVdsVolume::Mount, 3");
          VdsLogError(0xC2000010, 0, 0, LastError, 0x20A0018u, 0);
          LastError = -2147212223;
        }
        else
        {
          LastError = -2147212220;
        }
      }
      goto LABEL_10;
    }
    if ( (DWORD2(v21) & 0x40000) == 0 )
    {
LABEL_7:
      v11 = MountVolume(v10);
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      LastError = v11;
      goto LABEL_10;
    }
    hDevice = (HANDLE)-1LL;
    BytesReturned = 0;
    v13 = OpenDevice(v22, 3221225472LL, &hDevice);
    LastError = v13;
    v14 = v13 <= 0;
    if ( !v13 )
    {
      if ( !DeviceIoControl(hDevice, 0x56C008u, 0, 0, 0, 0, &BytesReturned, 0) )
      {
        LastError = GetLastError();
        VdsTraceEx(94, 0, "CVdsVolume::Mount, 4, %lX", LastError);
        if ( LastError <= 0 )
          goto LABEL_26;
        LastError = (unsigned __int16)LastError;
        goto LABEL_25;
      }
      v13 = MountVolume(v22);
      LastError = v13;
      v14 = v13 <= 0;
    }
    if ( v14 )
    {
LABEL_26:
      CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(&hDevice);
      goto LABEL_10;
    }
    LastError = (unsigned __int16)v13;
LABEL_25:
    LastError |= 0x80070000;
    goto LABEL_26;
  }
  CloseHandle(v6);
  *((_QWORD *)this + 17) = -1;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13), &v19);
  LastError = v7;
  if ( v7 >= 0 )
  {
    v10 = v22;
    v16 = v22;
    goto LABEL_7;
  }
  v9 = "CVdsVolume::Mount, 1, (%S) failed: %lX";
LABEL_13:
  VdsTraceEx(94, 0, v9, v22, v7);
LABEL_10:
  CVdsCoTaskPtr<unsigned short>::~CVdsCoTaskPtr<unsigned short>(&v16);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v18);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14001ffa0  mov     [rsp-8+arg_8], rbx
0x14001ffa5  mov     [rsp-8+arg_10], rsi
0x14001ffaa  push    rbp
0x14001ffab  push    rdi
0x14001ffac  push    r15
0x14001ffae  lea     rbp, [rsp-47h]
0x14001ffb3  sub     rsp, 0B0h
0x14001ffba  mov     rax, cs:__security_cookie
0x14001ffc1  xor     rax, rsp
0x14001ffc4  mov     [rbp+57h+var_20], rax
0x14001ffc8  mov     rbx, rcx
0x14001ffcb  lea     r8, aCvdsvolumeMoun; "CVdsVolume::Mount()"
0x14001ffd2  mov     r15d, 5Eh ; '^'
0x14001ffd8  mov     edx, r15d
0x14001ffdb  lea     rcx, [rbp+57h+var_68]
0x14001ffdf  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14001ffe5  nop
0x14001ffe6  xorps   xmm0, xmm0
0x14001ffe9  xor     eax, eax
0x14001ffeb  movups  [rbp+57h+var_58], xmm0
0x14001ffef  movups  [rbp+57h+var_48], xmm0
0x14001fff3  movups  [rbp+57h+var_38], xmm0
0x14001fff7  mov     [rbp+57h+var_28], rax
0x14001fffb  mov     [rbp+57h+var_78], rax
0x14001ffff  lea     rsi, [rbx-18h]
0x140020003  lea     edx, [rax+0Bh]; unsigned int
0x140020006  mov     rcx, rsi; this
0x140020009  call    ?ValidateCall@CVdsVolume@@AEAAJK@Z; CVdsVolume::ValidateCall(ulong)
0x14002000e  mov     edi, eax
0x140020010  test    eax, eax
0x140020012  jns     short loc_140020042
0x140020014  mov     r9d, eax
0x140020017  lea     r8, aCvdsvolumeMoun_0; "CVdsVolume::Mount, .5, hr=%lX"
0x14002001e  xor     edx, edx
0x140020020  mov     ecx, r15d
0x140020023  call    cs:__imp_VdsTraceEx
0x140020029  nop
0x14002002a  lea     rcx, [rbp+57h+var_78]
0x14002002e  call    ??1?$CVdsCoTaskPtr@G@@QEAA@XZ; CVdsCoTaskPtr<ushort>::~CVdsCoTaskPtr<ushort>(void)
0x140020033  nop
0x140020034  lea     rcx, [rbp+57h+var_68]
0x140020038  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14002003e  mov     eax, edi
0x140020040  jmp     short loc_1400200B8
0x140020042  mov     rcx, [rbx+88h]; hObject
0x140020049  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14002004d  cmp     rcx, rdi
0x140020050  jz      loc_1400200DC
0x140020056  call    cs:__imp_CloseHandle
0x14002005c  mov     [rbx+88h], rdi
0x140020063  mov     rcx, [rbx+68h]
0x140020067  mov     rax, [rcx]
0x14002006a  lea     rdx, [rbp+57h+var_58]
0x14002006e  mov     rax, [rax+18h]
0x140020072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020077  mov     ebx, eax
0x140020079  test    eax, eax
0x14002007b  jns     short loc_140020086
0x14002007d  lea     r8, aCvdsvolumeMoun_3; "CVdsVolume::Mount, 1, (%S) failed: %lX"
0x140020084  jmp     short loc_1400200FD
0x140020086  mov     rcx, [rbp+57h+var_28]
0x14002008a  mov     [rbp+57h+var_78], rcx
0x14002008e  call    cs:__imp_MountVolume
0x140020094  test    eax, eax
0x140020096  jle     short loc_1400200A0
0x140020098  movzx   eax, ax
0x14002009b  or      eax, 80070000h
0x1400200a0  mov     ebx, eax
0x1400200a2  lea     rcx, [rbp+57h+var_78]
0x1400200a6  call    ??1?$CVdsCoTaskPtr@G@@QEAA@XZ; CVdsCoTaskPtr<ushort>::~CVdsCoTaskPtr<ushort>(void)
0x1400200ab  nop
0x1400200ac  lea     rcx, [rbp+57h+var_68]
0x1400200b0  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x1400200b6  mov     eax, ebx
0x1400200b8  mov     rcx, [rbp+57h+var_20]
0x1400200bc  xor     rcx, rsp; StackCookie
0x1400200bf  call    __security_check_cookie
0x1400200c4  lea     r11, [rsp+0C0h+var_10]
0x1400200cc  mov     rbx, [r11+28h]
0x1400200d0  mov     rsi, [r11+30h]
0x1400200d4  mov     rsp, r11
0x1400200d7  pop     r15
0x1400200d9  pop     rdi
0x1400200da  pop     rbp
0x1400200db  retn
0x1400200dc  mov     rcx, [rbx+68h]
0x1400200e0  mov     rax, [rcx]
0x1400200e3  lea     rdx, [rbp+57h+var_58]
0x1400200e7  mov     rax, [rax+18h]
0x1400200eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400200f0  mov     ebx, eax
0x1400200f2  test    eax, eax
0x1400200f4  jns     short loc_140020112
0x1400200f6  lea     r8, aCvdsvolumeMoun_2; "CVdsVolume::Mount, 2, (%S) failed: %lX"
0x1400200fd  mov     r9, [rbp+57h+var_28]
0x140020101  mov     dword ptr [rsp+0C0h+lpOutBuffer], eax
0x140020105  xor     edx, edx
0x140020107  mov     ecx, r15d
0x14002010a  call    cs:__imp_VdsTraceEx
0x140020110  jmp     short loc_1400200A2
0x140020112  mov     rcx, [rbp+57h+var_28]
0x140020116  mov     [rbp+57h+var_78], rcx
0x14002011a  cmp     dword ptr [rbp+57h+var_48+4], 5
0x14002011e  jnz     short loc_14002012A
0x140020120  mov     ebx, 80042431h
0x140020125  jmp     loc_1400200A2
0x14002012a  test    rcx, rcx
0x14002012d  jnz     short loc_14002018B
0x14002012f  mov     rcx, rsi; this
0x140020132  call    ?IsPackOffline@CVdsVolume@@AEAAJXZ; CVdsVolume::IsPackOffline(void)
0x140020137  mov     ebx, eax
0x140020139  test    eax, eax
0x14002013b  js      loc_1400200A2
0x140020141  test    eax, eax
0x140020143  jnz     short loc_14002014F
0x140020145  mov     ebx, 80042444h
0x14002014a  jmp     loc_1400200A2
0x14002014f  lea     rdx, aCvdsvolumeMoun_1; "CVdsVolume::Mount, 3"
0x140020156  xor     ecx, ecx
0x140020158  call    cs:__imp_VdsTraceW
0x14002015e  mov     qword ptr [rsp+0C0h+nOutBufferSize], 0; unsigned __int16 *
0x140020167  mov     dword ptr [rsp+0C0h+lpOutBuffer], 20A0018h; unsigned int
0x14002016f  mov     r9d, ebx; unsigned int
0x140020172  xor     r8d, r8d; void *
0x140020175  xor     edx, edx; unsigned int
0x140020177  mov     ecx, 0C2000010h; unsigned int
0x14002017c  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140020181  mov     ebx, 80042441h
0x140020186  jmp     loc_1400200A2
0x14002018b  test    dword ptr [rbp+57h+var_38+8], 40000h
0x140020192  jz      loc_14002008E
0x140020198  mov     [rbp+57h+hDevice], rdi
0x14002019c  mov     [rbp+57h+BytesReturned], 0
0x1400201a3  lea     r8, [rbp+57h+hDevice]
0x1400201a7  mov     edx, 0C0000000h
0x1400201ac  mov     rcx, [rbp+57h+var_28]
0x1400201b0  call    cs:__imp_OpenDevice
0x1400201b6  mov     ebx, eax
0x1400201b8  test    eax, eax
0x1400201ba  jz      short loc_1400201D5
0x1400201bc  jle     short loc_1400201C7
0x1400201be  movzx   ebx, ax
0x1400201c1  or      ebx, 80070000h
0x1400201c7  lea     rcx, [rbp+57h+hDevice]
0x1400201cb  call    ??1?$CVdsHandleImpl@$0?0@@QEAA@XZ; CVdsHandleImpl<-1>::~CVdsHandleImpl<-1>(void)
0x1400201d0  jmp     loc_1400200A2
0x1400201d5  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x1400201de  lea     rax, [rbp+57h+BytesReturned]
0x1400201e2  mov     [rsp+0C0h+lpBytesReturned], rax; lpBytesReturned
0x1400201e7  mov     [rsp+0C0h+nOutBufferSize], 0; nOutBufferSize
0x1400201ef  mov     [rsp+0C0h+lpOutBuffer], 0; lpOutBuffer
0x1400201f8  xor     r9d, r9d; nInBufferSize
0x1400201fb  xor     r8d, r8d; lpInBuffer
0x1400201fe  mov     edx, 56C008h; dwIoControlCode
0x140020203  mov     rcx, [rbp+57h+hDevice]; hDevice
0x140020207  call    cs:__imp_DeviceIoControl
0x14002020d  test    eax, eax
0x14002020f  jnz     short loc_140020237
0x140020211  call    cs:__imp_GetLastError
0x140020217  mov     ebx, eax
0x140020219  mov     r9d, eax
0x14002021c  lea     r8, aCvdsvolumeMoun_4; "CVdsVolume::Mount, 4, %lX"
0x140020223  xor     edx, edx
0x140020225  mov     ecx, r15d
0x140020228  call    cs:__imp_VdsTraceEx
0x14002022e  test    ebx, ebx
0x140020230  jle     short loc_1400201C7
0x140020232  movzx   ebx, bx
0x140020235  jmp     short loc_1400201C1
0x140020237  mov     rcx, [rbp+57h+var_28]
0x14002023b  call    cs:__imp_MountVolume
0x140020241  mov     ebx, eax
0x140020243  test    eax, eax
0x140020245  jmp     loc_1400201BC
```
