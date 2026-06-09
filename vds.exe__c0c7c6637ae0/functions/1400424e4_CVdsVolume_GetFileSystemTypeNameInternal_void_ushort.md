# CVdsVolume::GetFileSystemTypeNameInternal(void *,ushort * *)

- ea: `0x1400424e4`
- end: `0x140042673`
- name: `?GetFileSystemTypeNameInternal@CVdsVolume@@SAJPEAXPEAPEAG@Z`
- size: `399`
- prototype: `__int64 __fastcall(HANDLE FileHandle, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140021b50`
- `0x140042230`

## callees

- `0x140003710`
- `0x140004360`
- `0x140013298`
- `0x14002e123`
- `0x14003cd8c`
- `0x1400424e4`
- `0x140052e80`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x140042579`
- `ntdll!NtQueryVolumeInformationFile` at `0x140042579`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400425ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400425ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140042625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140042625`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004253a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004253a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140042647`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140042647`
- `vdsutil!VdsTraceW` at `0x140042591`
- `vdsutil!VdsTraceW` at `0x1400425ed`
- `vdsutil!VdsTraceW` at `0x14004261c`
- `vdsutil!VdsTraceW` at `0x140042591`
- `vdsutil!VdsTraceW` at `0x1400425ed`
- `vdsutil!VdsTraceW` at `0x14004261c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsVolume::GetFileSystemTypeNameInternal(HANDLE FileHandle, unsigned __int16 **a2)
{
  signed int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi
  int v10; // eax
  __int64 v11; // r11
  __int64 v13; // [rsp+30h] [rbp-49h] BYREF
  int v14; // [rsp+38h] [rbp-41h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v16[16]; // [rsp+50h] [rbp-29h] BYREF
  _BYTE FsInformation[8]; // [rsp+60h] [rbp-19h] BYREF
  unsigned int v18; // [rsp+68h] [rbp-11h]
  unsigned __int16 v19[34]; // [rsp+6Ch] [rbp-Dh] BYREF

  IoStatusBlock = 0;
  memset_0(FsInformation, 0, 0x50u);
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v16, 0x5Eu, "CVdsVolume::GetFileSystemTypeNameInternal()");
  v13 = 0;
  v14 = 0;
  v4 = CVdsOperationEntry::BeginOperation((CVdsOperationEntry *)&v13);
  if ( v4 >= 0 )
  {
    v5 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x50u, FileFsAttributeInformation);
    v6 = v5;
    if ( v5 )
    {
      VdsTraceW(0, L"CVdsVolume::GetFileSystemTypeNameInternal, 1, status=%lX", v5);
      VdsLogError(0xC2000001, 0, 0, v6, 0x20A0009u, 0);
      v4 = v6 | 0x10000000;
    }
    else
    {
      v7 = v18 >> 1;
      v8 = (unsigned __int16 *)CoTaskMemAlloc(2LL * ((v18 >> 1) + 1));
      v9 = v8;
      if ( v8 )
      {
        v10 = StringCchCopyNW(v8, v7 + 1, v19, v7);
        v4 = v10;
        if ( v10 >= 0 )
        {
          v9[v11] = 0;
          *a2 = v9;
          v4 = 0;
        }
        else
        {
          VdsTraceW(0, L"CVdsVolume::GetFileSystemTypeNameInternal, 3, hr=%lX", (unsigned int)v10);
          CoTaskMemFree(v9);
        }
      }
      else
      {
        v4 = -2147024882;
        VdsTraceW(0, L"CVdsVolume::GetFileSystemTypeNameInternal, 2, hr=%lX", 2147942414LL);
      }
    }
  }
  CVdsOperationEntry::~CVdsOperationEntry((CVdsOperationEntry *)&v13);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400424e4  mov     [rsp-8+arg_10], rbx
0x1400424e9  mov     [rsp-8+arg_18], rsi
0x1400424ee  push    rbp
0x1400424ef  push    rdi
0x1400424f0  push    r14
0x1400424f2  lea     rbp, [rsp-47h]
0x1400424f7  sub     rsp, 0C0h
0x1400424fe  mov     rax, cs:__security_cookie
0x140042505  xor     rax, rsp
0x140042508  mov     [rbp+57h+var_20], rax
0x14004250c  mov     r14, rdx
0x14004250f  mov     rdi, rcx
0x140042512  xorps   xmm0, xmm0
0x140042515  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140042519  mov     esi, 50h ; 'P'
0x14004251e  mov     r8d, esi; Size
0x140042521  xor     edx, edx; Val
0x140042523  lea     rcx, [rbp+57h+FsInformation]; void *
0x140042527  call    memset_0
0x14004252c  lea     r8, aCvdsvolumeGetf_24; "CVdsVolume::GetFileSystemTypeNameIntern"...
0x140042533  lea     edx, [rsi+0Eh]
0x140042536  lea     rcx, [rbp+57h+var_80]
0x14004253a  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140042540  nop
0x140042541  mov     [rbp+57h+var_A0], 0
0x140042549  mov     [rbp+57h+var_98], 0
0x140042550  lea     rcx, [rbp+57h+var_A0]; this
0x140042554  call    ?BeginOperation@CVdsOperationEntry@@QEAAJXZ; CVdsOperationEntry::BeginOperation(void)
0x140042559  mov     ebx, eax
0x14004255b  test    eax, eax
0x14004255d  js      loc_140042639
0x140042563  mov     [rsp+0D0h+FsInformationClass], 5; FsInformationClass
0x14004256b  mov     r9d, esi; Length
0x14004256e  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x140042572  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140042576  mov     rcx, rdi; FileHandle
0x140042579  call    cs:__imp_NtQueryVolumeInformationFile
0x14004257f  mov     ebx, eax
0x140042581  test    eax, eax
0x140042583  jz      short loc_1400425C0
0x140042585  mov     r8d, eax
0x140042588  lea     rdx, aCvdsvolumeGetf_5; "CVdsVolume::GetFileSystemTypeNameIntern"...
0x14004258f  xor     ecx, ecx
0x140042591  call    cs:__imp_VdsTraceW
0x140042597  mov     [rsp+0D0h+var_A8], 0; unsigned __int16 *
0x1400425a0  mov     [rsp+0D0h+FsInformationClass], 20A0009h; unsigned int
0x1400425a8  mov     r9d, ebx; unsigned int
0x1400425ab  xor     r8d, r8d; void *
0x1400425ae  xor     edx, edx; unsigned int
0x1400425b0  mov     ecx, 0C2000001h; unsigned int
0x1400425b5  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x1400425ba  bts     ebx, 1Ch
0x1400425be  jmp     short loc_140042639
0x1400425c0  mov     ebx, [rbp+57h+var_68]
0x1400425c3  shr     ebx, 1
0x1400425c5  lea     eax, [rbx+1]
0x1400425c8  mov     esi, eax
0x1400425ca  lea     rcx, [rax+rax]; cb
0x1400425ce  call    cs:__imp_CoTaskMemAlloc
0x1400425d4  mov     rdi, rax
0x1400425d7  test    rax, rax
0x1400425da  jnz     short loc_1400425F5
0x1400425dc  mov     ebx, 8007000Eh
0x1400425e1  mov     r8d, ebx
0x1400425e4  lea     rdx, aCvdsvolumeGetf_10; "CVdsVolume::GetFileSystemTypeNameIntern"...
0x1400425eb  xor     ecx, ecx
0x1400425ed  call    cs:__imp_VdsTraceW
0x1400425f3  jmp     short loc_140042639
0x1400425f5  mov     r11d, ebx
0x1400425f8  mov     r9d, ebx; unsigned __int64
0x1400425fb  lea     r8, [rbp+57h+var_64]; unsigned __int16 *
0x1400425ff  mov     rdx, rsi; unsigned __int64
0x140042602  mov     rcx, rdi; unsigned __int16 *
0x140042605  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14004260a  mov     ebx, eax
0x14004260c  test    eax, eax
0x14004260e  jns     short loc_14004262D
0x140042610  mov     r8d, eax
0x140042613  lea     rdx, aCvdsvolumeGetf_20; "CVdsVolume::GetFileSystemTypeNameIntern"...
0x14004261a  xor     ecx, ecx
0x14004261c  call    cs:__imp_VdsTraceW
0x140042622  mov     rcx, rdi; pv
0x140042625  call    cs:__imp_CoTaskMemFree
0x14004262b  jmp     short loc_140042639
0x14004262d  xor     eax, eax
0x14004262f  mov     [rdi+r11*2], ax
0x140042634  mov     [r14], rdi
0x140042637  xor     ebx, ebx
0x140042639  lea     rcx, [rbp+57h+var_A0]; this
0x14004263d  call    ??1CVdsOperationEntry@@QEAA@XZ; CVdsOperationEntry::~CVdsOperationEntry(void)
0x140042642  nop
0x140042643  lea     rcx, [rbp+57h+var_80]
0x140042647  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14004264d  mov     eax, ebx
0x14004264f  mov     rcx, [rbp+57h+var_20]
0x140042653  xor     rcx, rsp; StackCookie
0x140042656  call    __security_check_cookie
0x14004265b  lea     r11, [rsp+0D0h+var_10]
0x140042663  mov     rbx, [r11+30h]
0x140042667  mov     rsi, [r11+38h]
0x14004266b  mov     rsp, r11
0x14004266e  pop     r14
0x140042670  pop     rdi
0x140042671  pop     rbp
0x140042672  retn
```
