# CFsrmTargetProcessHandle::InitializeFromPID(ulong)

- ea: `0x18005dc7c`
- end: `0x18005de4b`
- name: `?InitializeFromPID@CFsrmTargetProcessHandle@@QEAAXK@Z`
- size: `463`
- prototype: `void(CFsrmTargetProcessHandle *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callers

- `0x18009cf88`

## callees

- `0x180006a1c`
- `0x1800095f4`
- `0x18005dc7c`
- `0x18005de54`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18005dd71`
- `KERNEL32!CloseHandle` at `0x18005dd71`
- `KERNEL32!GetCurrentProcessId` at `0x18005dd2a`
- `KERNEL32!GetCurrentProcessId` at `0x18005dd2a`
- `KERNEL32!OpenProcess` at `0x18005dd46`
- `KERNEL32!OpenProcess` at `0x18005dd46`

## string_xrefs

- `0x18005dcad`: `base\fs\fsrm\service\stream\streamlib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CFsrmTargetProcessHandle::InitializeFromPID(CFsrmTargetProcessHandle *this, DWORD a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE v5; // rsi
  void *v6; // rcx
  char v7; // al
  char Hr; // al
  char v9; // al
  _QWORD v10[3]; // [rsp+28h] [rbp-D8h] BYREF
  int v11; // [rsp+40h] [rbp-C0h]
  int v12; // [rsp+44h] [rbp-BCh]
  int v13; // [rsp+48h] [rbp-B8h]
  _BYTE v14[96]; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+B0h] [rbp-50h]
  void **v16; // [rsp+C0h] [rbp-40h] BYREF
  int v17; // [rsp+C8h] [rbp-38h]

  v10[0] = L"base\\fs\\fsrm\\service\\stream\\streamlib.cpp";
  v10[1] = L"CFsrmTargetProcessHandle::InitializeFromPID";
  v10[2] = L"STREAMLC";
  v11 = 1766;
  v12 = 17;
  v13 = 255;
  v15 = 0x1000000;
  memset_0(v14, 0, sizeof(v14));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v16, (const struct CSrmDebugInfo *)v10, 0);
  if ( *((_DWORD *)this + 4) )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v16, -2147418113);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v16);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v16, 0x6EBu, Hr, 0, v10);
  }
  v17 = 0;
  CurrentProcessId = GetCurrentProcessId();
  *((_DWORD *)this + 5) = CurrentProcessId == a2;
  if ( CurrentProcessId != a2 )
  {
    v5 = OpenProcess(0x100040u, 0, a2);
    if ( !v5 )
    {
      CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v16, -2147200188);
      v9 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v16);
      CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v16, 0x6F3u, v9, 0, v10);
    }
    v17 = 0;
    *((_DWORD *)this + 4) = a2;
    v6 = (void *)*((_QWORD *)this + 1);
    if ( v6 )
      CloseHandle(v6);
    *((_QWORD *)this + 1) = v5;
  }
  if ( !(unsigned int)CFsrmTargetProcessHandle::IsTargetProcessAlive(this) )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v16, -2147200188);
    v7 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v16);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v16, 0x6FAu, v7, 0, v10);
  }
  v17 = 0;
  v16 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v16);
}

```

## disassembly

```asm
0x18005dc7c  mov     [rsp-8+arg_10], rbx
0x18005dc81  push    rbp
0x18005dc82  push    rsi
0x18005dc83  push    rdi
0x18005dc84  lea     rbp, [rsp-80h]
0x18005dc89  sub     rsp, 180h
0x18005dc90  mov     rax, cs:__security_cookie
0x18005dc97  xor     rax, rsp
0x18005dc9a  mov     [rbp+90h+var_20], rax
0x18005dc9e  mov     edi, edx
0x18005dca0  mov     rbx, rcx
0x18005dca3  lea     rax, [rsp+190h+var_168]
0x18005dca8  mov     [rsp+190h+var_170], rax
0x18005dcad  lea     rax, aBaseFsFsrmServ_12; "base\\fs\\fsrm\\service\\stream\\stream"...
0x18005dcb4  mov     [rsp+190h+var_168], rax
0x18005dcb9  lea     rax, aCfsrmtargetpro_1; "CFsrmTargetProcessHandle::InitializeFro"...
0x18005dcc0  mov     [rsp+190h+var_160], rax
0x18005dcc5  lea     rax, aStreamlc; "STREAMLC"
0x18005dccc  mov     [rsp+190h+var_158], rax
0x18005dcd1  mov     [rsp+190h+var_150], 6E6h
0x18005dcd9  mov     [rsp+190h+var_14C], 11h
0x18005dce1  mov     [rsp+190h+var_148], 0FFh
0x18005dce9  mov     [rbp+90h+var_E0], 1000000h
0x18005dcf0  xor     edx, edx; Val
0x18005dcf2  lea     r8d, [rdx+60h]; Size
0x18005dcf6  lea     rcx, [rsp+190h+var_140]; void *
0x18005dcfb  call    memset_0
0x18005dd00  nop
0x18005dd01  xor     r8d, r8d
0x18005dd04  lea     rdx, [rsp+190h+var_168]
0x18005dd09  lea     rcx, [rbp+90h+var_D0]
0x18005dd0d  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18005dd12  nop
0x18005dd13  mov     eax, [rbp+90h+var_C8]
0x18005dd16  mov     [rbp+90h+var_C8], eax
0x18005dd19  cmp     dword ptr [rbx+10h], 0
0x18005dd1d  jnz     loc_18005DDF3
0x18005dd23  mov     [rbp+90h+var_C8], 0
0x18005dd2a  call    cs:__imp_GetCurrentProcessId
0x18005dd30  xor     ecx, ecx
0x18005dd32  cmp     eax, edi
0x18005dd34  setz    cl
0x18005dd37  mov     [rbx+14h], ecx
0x18005dd3a  jz      short loc_18005DD7B
0x18005dd3c  mov     r8d, edi; dwProcessId
0x18005dd3f  xor     edx, edx; bInheritHandle
0x18005dd41  mov     ecx, 100040h; dwDesiredAccess
0x18005dd46  call    cs:__imp_OpenProcess
0x18005dd4c  mov     rsi, rax
0x18005dd4f  mov     ecx, [rbp+90h+var_C8]
0x18005dd52  mov     [rbp+90h+var_C8], ecx
0x18005dd55  test    rax, rax
0x18005dd58  jz      loc_18005DE1F
0x18005dd5e  mov     [rbp+90h+var_C8], 0
0x18005dd65  mov     [rbx+10h], edi
0x18005dd68  mov     rcx, [rbx+8]; hObject
0x18005dd6c  test    rcx, rcx
0x18005dd6f  jz      short loc_18005DD77
0x18005dd71  call    cs:__imp_CloseHandle
0x18005dd77  mov     [rbx+8], rsi
0x18005dd7b  mov     eax, [rbp+90h+var_C8]
0x18005dd7e  mov     [rbp+90h+var_C8], eax
0x18005dd81  mov     rcx, rbx; this
0x18005dd84  call    ?IsTargetProcessAlive@CFsrmTargetProcessHandle@@QEAAHXZ; CFsrmTargetProcessHandle::IsTargetProcessAlive(void)
0x18005dd89  test    eax, eax
0x18005dd8b  jz      short loc_18005DDC7
0x18005dd8d  mov     [rbp+90h+var_C8], 0
0x18005dd94  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18005dd9b  mov     [rbp+90h+var_D0], rax
0x18005dd9f  lea     rcx, [rbp+90h+var_D0]; this
0x18005dda3  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18005dda8  mov     rcx, [rbp+90h+var_20]
0x18005ddac  xor     rcx, rsp; StackCookie
0x18005ddaf  call    __security_check_cookie
0x18005ddb4  mov     rbx, [rsp+190h+arg_10]
0x18005ddbc  add     rsp, 180h
0x18005ddc3  pop     rdi
0x18005ddc4  pop     rsi
0x18005ddc5  pop     rbp
0x18005ddc6  retn
0x18005ddc7  mov     edx, 80045344h; int
0x18005ddcc  lea     rcx, [rbp+90h+var_D0]; this
0x18005ddd0  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005ddd5  lea     rcx, [rbp+90h+var_D0]; this
0x18005ddd9  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005ddde  mov     r8d, eax; char
0x18005dde1  xor     r9d, r9d; unsigned __int16 *
0x18005dde4  mov     edx, 6FAh; unsigned int
0x18005dde9  lea     rcx, [rbp+90h+var_D0]; this
0x18005dded  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005ddf3  mov     edx, 8000FFFFh; int
0x18005ddf8  lea     rcx, [rbp+90h+var_D0]; this
0x18005ddfc  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005de01  lea     rcx, [rbp+90h+var_D0]; this
0x18005de05  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005de0a  mov     r8d, eax; char
0x18005de0d  xor     r9d, r9d; unsigned __int16 *
0x18005de10  mov     edx, 6EBh; unsigned int
0x18005de15  lea     rcx, [rbp+90h+var_D0]; this
0x18005de19  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18005de1f  mov     edx, 80045344h; int
0x18005de24  lea     rcx, [rbp+90h+var_D0]; this
0x18005de28  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18005de2d  lea     rcx, [rbp+90h+var_D0]; this
0x18005de31  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18005de36  mov     r8d, eax; char
0x18005de39  xor     r9d, r9d; unsigned __int16 *
0x18005de3c  mov     edx, 6F3h; unsigned int
0x18005de41  lea     rcx, [rbp+90h+var_D0]; this
0x18005de45  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
```
