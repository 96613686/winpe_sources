# ctrlc_hndl(ulong)

- ea: `0x10040bde0`
- end: `0x10040beaf`
- name: `?ctrlc_hndl@@YAHK@Z`
- size: `207`
- prototype: `BOOL __stdcall(DWORD CtrlType)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x10040ba70`
- `0x10040bde0`

## import_xrefs

- `sqldk!?sm_WorkerLsBitmap@SOS_PublicGlobals@@2VSmallBitmap@@A` at `0x10040be16`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040be88`
- `sqldk!??1AutoMakeMicroSOSThread@@QEAA@XZ` at `0x10040be88`
- `sqldk!??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z` at `0x10040be74`
- `sqldk!??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z` at `0x10040be74`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ctrlc_hndl(DWORD CtrlType)
{
  __int64 v2; // r8
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rdx
  void *v5; // rsp
  void *v6; // rsp
  void **v7; // r9
  unsigned int v8; // ebx
  __int64 v10; // [rsp+40h] [rbp+0h] BYREF
  _BYTE v11[6048]; // [rsp+50h] [rbp+10h] BYREF

  v10 = -2;
  v2 = SOS_PublicGlobals::sm_WorkerLsBitmap[1];
  if ( v2 )
  {
    v3 = 8 * v2 + 15;
    if ( v3 <= 8 * v2 )
      v3 = 0xFFFFFFFFFFFFFF0LL;
    v4 = v3 & 0xFFFFFFFFFFFFFFF0uLL;
    v5 = alloca(v4);
    v6 = alloca(v4);
    v7 = (void **)&v10;
  }
  else
  {
    v7 = 0;
  }
  AutoMakeMicroSOSThread::AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v11, 0, v2, v7, 1, 0, 0);
  v8 = ctrlc_hndl_seh(CtrlType);
  AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread((AutoMakeMicroSOSThread *)v11);
  return v8;
}

```

## disassembly

```asm
0x10040bde0  push    rbp
0x10040bde2  mov     eax, 1800h
0x10040bde7  call    _alloca_probe
0x10040bdec  sub     rsp, rax
0x10040bdef  lea     rbp, [rsp+40h]
0x10040bdf4  mov     [rbp+17C0h+var_17C0], 0FFFFFFFFFFFFFFFEh
0x10040bdfc  mov     [rbp+17C0h+arg_0], rbx
0x10040be03  mov     rax, cs:__security_cookie
0x10040be0a  xor     rax, rbp
0x10040be0d  mov     [rbp+17C0h+var_10], rax
0x10040be14  mov     ebx, ecx
0x10040be16  mov     rax, cs:__imp_?sm_WorkerLsBitmap@SOS_PublicGlobals@@2VSmallBitmap@@A; SmallBitmap SOS_PublicGlobals::sm_WorkerLsBitmap
0x10040be1d  mov     r8, [rax+8]
0x10040be21  xor     ecx, ecx
0x10040be23  test    r8, r8
0x10040be26  jz      short loc_10040BE59
0x10040be28  lea     rax, ds:0[r8*8]
0x10040be30  lea     rdx, [rax+0Fh]
0x10040be34  cmp     rdx, rax
0x10040be37  ja      short loc_10040BE43
0x10040be39  mov     rdx, 0FFFFFFFFFFFFFF0h
0x10040be43  and     rdx, 0FFFFFFFFFFFFFFF0h
0x10040be47  mov     rax, rdx
0x10040be4a  call    _alloca_probe
0x10040be4f  sub     rsp, rdx
0x10040be52  lea     r9, [rsp+1800h+var_17C0]
0x10040be57  jmp     short loc_10040BE5C
0x10040be59  mov     r9, rcx
0x10040be5c  mov     [rsp+1800h+var_17D0], rcx
0x10040be61  mov     [rsp+1800h+var_17D8], rcx
0x10040be66  mov     [rsp+1800h+var_17E0], 1
0x10040be6e  xor     edx, edx
0x10040be70  lea     rcx, [rbp+17C0h+var_17B0]
0x10040be74  call    cs:__imp_??0AutoMakeMicroSOSThread@@QEAA@QEAX_JPEAPEAXHPEAVSOS_Scheduler@@PEAVIMemObj@@@Z; AutoMakeMicroSOSThread::AutoMakeMicroSOSThread(void * const,__int64,void * *,int,SOS_Scheduler *,IMemObj *)
0x10040be7a  nop
0x10040be7b  mov     ecx, ebx; unsigned int
0x10040be7d  call    ?ctrlc_hndl_seh@@YAHK@Z; ctrlc_hndl_seh(ulong)
0x10040be82  mov     ebx, eax
0x10040be84  lea     rcx, [rbp+17C0h+var_17B0]
0x10040be88  call    cs:__imp_??1AutoMakeMicroSOSThread@@QEAA@XZ; AutoMakeMicroSOSThread::~AutoMakeMicroSOSThread(void)
0x10040be8e  mov     eax, ebx
0x10040be90  mov     rcx, [rbp+17C0h+var_10]
0x10040be97  xor     rcx, rbp; StackCookie
0x10040be9a  call    __security_check_cookie
0x10040be9f  mov     rbx, [rbp+17C0h+arg_0]
0x10040bea6  lea     rsp, [rbp+17C0h]
0x10040bead  pop     rbp
0x10040beae  retn
```
