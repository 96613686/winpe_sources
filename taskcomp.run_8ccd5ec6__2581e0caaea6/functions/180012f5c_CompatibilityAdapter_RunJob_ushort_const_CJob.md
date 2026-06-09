# CompatibilityAdapter::RunJob(ushort const *,CJob *)

- ea: `0x180012f5c`
- end: `0x1800130b0`
- name: `?RunJob@CompatibilityAdapter@@AEAAJPEBGPEAVCJob@@@Z`
- size: `340`
- prototype: `int(CompatibilityAdapter *__hidden this, const unsigned __int16 *, struct CJob *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800111e0`

## callees

- `0x180005c10`
- `0x18000af88`
- `0x18000c588`
- `0x180011894`
- `0x180011908`
- `0x180012f5c`
- `0x180024c24`
- `0x1800267fc`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180012fb6`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180012fb6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CompatibilityAdapter::RunJob(
        CompatibilityAdapter *this,
        const unsigned __int16 *a2,
        struct CJob *a3)
{
  __int64 v6; // rcx
  int v7; // ebx
  unsigned int v8; // r8d
  const unsigned __int16 **v9; // r9
  int v10; // r8d
  char *v11; // r9
  tsched *v12; // rcx
  int v13; // eax
  unsigned int v14; // eax
  int *v15; // [rsp+28h] [rbp-280h]
  char v16[32]; // [rsp+0h] [rbp-2A8h] BYREF
  unsigned int v17; // [rsp+20h] [rbp-288h]
  unsigned int v18; // [rsp+28h] [rbp-280h]
  const unsigned __int16 *v19; // [rsp+30h] [rbp-278h]
  int v20; // [rsp+40h] [rbp-268h] BYREF
  RpcSession *v21; // [rsp+48h] [rbp-260h] BYREF
  FILETIME FileTime; // [rsp+50h] [rbp-258h] BYREF
  struct CJob *v23; // [rsp+58h] [rbp-250h]
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-248h] BYREF
  struct _GUID v25; // [rsp+70h] [rbp-238h] BYREF
  unsigned __int16 v26[264]; // [rsp+80h] [rbp-228h] BYREF

  v23 = a3;
  if ( !CompatibilityAdapter::GetAdapter() )
    return 2147500037LL;
  FileTime = GetLocalTimeAsFileTime();
  SystemTime = 0;
  FileTimeToSystemTime(&FileTime, &SystemTime);
  memset_0(v26, 0, 0x20Au);
  v7 = FilenameToUri(a2, v26);
  v20 = v7;
  if ( v7 >= 0 )
  {
    try
    {
      CompatibilityAdapter::GetSession(v6, &v21);
      v25 = 0;
      v7 = RpcSession::RunTask(v21, v26, v8, v9, v17, v18, v19, &v25);
      v20 = v7;
      v12 = v21;
      if ( v21 )
        wmi::RefBase::Release(v21);
    }
    catch ( ... )
    {
      tsched::KnownExceptionToHResult(v12, v16, v10, v11, (unsigned __int8)&v20, v15);
    }
  }
  v13 = *((_DWORD *)a3 + 22);
  if ( v7 < 0 )
  {
    *((_DWORD *)a3 + 48) = v7;
    v14 = v13 | 0x80000;
  }
  else
  {
    *((_DWORD *)a3 + 48) = 0;
    *((struct _SYSTEMTIME *)a3 + 6) = SystemTime;
    v14 = v13 & 0xFFF7FFFF;
  }
  *((_DWORD *)a3 + 22) = v14 & 0xDBFF7FFF | 0x20000000;
  return CJob::SaveWithRetry(a3, 0, 0, 5u);
}

```

## disassembly

```asm
0x180012f5c  mov     [rsp+arg_0], rbx
0x180012f61  push    rdi
0x180012f62  sub     rsp, 2A0h
0x180012f69  mov     rax, cs:__security_cookie
0x180012f70  xor     rax, rsp
0x180012f73  mov     [rsp+2A8h+var_18], rax
0x180012f7b  mov     rdi, r8
0x180012f7e  mov     rbx, rdx
0x180012f81  mov     [rsp+2A8h+var_250], r8
0x180012f86  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x180012f8b  test    rax, rax
0x180012f8e  jnz     short loc_180012F9A
0x180012f90  mov     eax, 80004005h
0x180012f95  jmp     loc_18001308E
0x180012f9a  call    ?GetLocalTimeAsFileTime@@YA?AU_FILETIME@@XZ; GetLocalTimeAsFileTime(void)
0x180012f9f  mov     qword ptr [rsp+2A8h+FileTime.dwLowDateTime], rax
0x180012fa4  xorps   xmm0, xmm0
0x180012fa7  movups  xmmword ptr [rsp+2A8h+SystemTime.wYear], xmm0
0x180012fac  lea     rdx, [rsp+2A8h+SystemTime]; lpSystemTime
0x180012fb1  lea     rcx, [rsp+2A8h+FileTime]; lpFileTime
0x180012fb6  call    cs:__imp_FileTimeToSystemTime
0x180012fbd  nop     dword ptr [rax+rax+00h]
0x180012fc2  nop
0x180012fc3  xor     edx, edx; Val
0x180012fc5  mov     r8d, 20Ah; Size
0x180012fcb  lea     rcx, [rsp+2A8h+var_228]; void *
0x180012fd3  call    memset_0
0x180012fd8  lea     rdx, [rsp+2A8h+var_228]; unsigned __int16 *
0x180012fe0  mov     rcx, rbx; unsigned __int16 *
0x180012fe3  call    ?FilenameToUri@@YAJPEBGPEAG@Z; FilenameToUri(ushort const *,ushort *)
0x180012fe8  mov     ebx, eax
0x180012fea  mov     [rsp+2A8h+var_268], eax
0x180012fee  test    eax, eax
0x180012ff0  jns     short loc_180012FF4
0x180012ff2  jmp     short loc_180013044
0x180012ff4  lea     rdx, [rsp+2A8h+var_260]
0x180012ff9  call    ?GetSession@CompatibilityAdapter@@QEBA?AV?$AutoRef@VRpcSession@@@wmi@@XZ; CompatibilityAdapter::GetSession(void)
0x180012ffe  nop
0x180012fff  xorps   xmm0, xmm0
0x180013002  movups  xmmword ptr [rsp+2A8h+var_238.Data1], xmm0
0x180013007  lea     rax, [rsp+2A8h+var_238]
0x18001300c  mov     [rsp+2A8h+var_270], rax; struct _GUID *
0x180013011  lea     rdx, [rsp+2A8h+var_228]; unsigned __int16 *
0x180013019  mov     rcx, [rsp+2A8h+var_260]; this
0x18001301e  call    ?RunTask@RpcSession@@QEBAJPEBGKPEAPEBGKK0PEAU_GUID@@@Z; RpcSession::RunTask(ushort const *,ulong,ushort const * *,ulong,ulong,ushort const *,_GUID *)
0x180013023  mov     ebx, eax
0x180013025  mov     [rsp+2A8h+var_268], eax
0x180013029  mov     rcx, [rsp+2A8h+var_260]; this
0x18001302e  test    rcx, rcx
0x180013031  jz      short loc_180013039
0x180013033  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x180013038  nop
0x180013039  jmp     short loc_180013044
0x18001303b  mov     ebx, [rsp+2A8h+var_268]
0x18001303f  mov     rdi, [rsp+2A8h+var_250]
0x180013044  mov     eax, [rdi+58h]
0x180013047  test    ebx, ebx
0x180013049  js      short loc_180013065
0x18001304b  mov     dword ptr [rdi+0C0h], 0
0x180013055  movups  xmm0, xmmword ptr [rsp+2A8h+SystemTime.wYear]
0x18001305a  movdqu  xmmword ptr [rdi+60h], xmm0
0x18001305f  btr     eax, 13h
0x180013063  jmp     short loc_18001306F
0x180013065  mov     [rdi+0C0h], ebx
0x18001306b  bts     eax, 13h
0x18001306f  and     eax, 0FBFF7FFFh
0x180013074  bts     eax, 1Dh
0x180013078  mov     [rdi+58h], eax
0x18001307b  mov     r9d, 5; unsigned int
0x180013081  xor     r8d, r8d; int
0x180013084  xor     edx, edx; lpFileName
0x180013086  mov     rcx, rdi; this
0x180013089  call    ?SaveWithRetry@CJob@@QEAAJPEBGHK@Z; CJob::SaveWithRetry(ushort const *,int,ulong)
0x18001308e  mov     rcx, [rsp+2A8h+var_18]
0x180013096  xor     rcx, rsp; StackCookie
0x180013099  call    __security_check_cookie
0x18001309e  mov     rbx, [rsp+2A8h+arg_0]
0x1800130a6  add     rsp, 2A0h
0x1800130ad  pop     rdi
0x1800130ae  retn
```
