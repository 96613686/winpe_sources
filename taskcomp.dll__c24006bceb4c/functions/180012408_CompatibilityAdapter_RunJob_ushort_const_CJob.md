# CompatibilityAdapter::RunJob(ushort const *,CJob *)

- ea: `0x180012408`
- end: `0x180012555`
- name: `?RunJob@CompatibilityAdapter@@AEAAJPEBGPEAVCJob@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(CompatibilityAdapter *this, const unsigned __int16 *, struct CJob *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010750`

## callees

- `0x1800058f0`
- `0x18000a994`
- `0x18000bd7c`
- `0x180010e44`
- `0x180010eb8`
- `0x180012408`
- `0x1800235d0`
- `0x180025090`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180012462`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180012462`

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
0x180012408  mov     [rsp+arg_0], rbx
0x18001240d  push    rdi
0x18001240e  sub     rsp, 2A0h
0x180012415  mov     rax, cs:__security_cookie
0x18001241c  xor     rax, rsp
0x18001241f  mov     [rsp+2A8h+var_18], rax
0x180012427  mov     rdi, r8
0x18001242a  mov     rbx, rdx
0x18001242d  mov     [rsp+2A8h+var_250], r8
0x180012432  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x180012437  test    rax, rax
0x18001243a  jnz     short loc_180012446
0x18001243c  mov     eax, 80004005h
0x180012441  jmp     loc_180012534
0x180012446  call    ?GetLocalTimeAsFileTime@@YA?AU_FILETIME@@XZ; GetLocalTimeAsFileTime(void)
0x18001244b  mov     qword ptr [rsp+2A8h+FileTime.dwLowDateTime], rax
0x180012450  xorps   xmm0, xmm0
0x180012453  movups  xmmword ptr [rsp+2A8h+SystemTime.wYear], xmm0
0x180012458  lea     rdx, [rsp+2A8h+SystemTime]; lpSystemTime
0x18001245d  lea     rcx, [rsp+2A8h+FileTime]; lpFileTime
0x180012462  call    cs:__imp_FileTimeToSystemTime
0x180012468  nop
0x180012469  xor     edx, edx; Val
0x18001246b  mov     r8d, 20Ah; Size
0x180012471  lea     rcx, [rsp+2A8h+var_228]; void *
0x180012479  call    memset_0
0x18001247e  lea     rdx, [rsp+2A8h+var_228]; unsigned __int16 *
0x180012486  mov     rcx, rbx; unsigned __int16 *
0x180012489  call    ?FilenameToUri@@YAJPEBGPEAG@Z; FilenameToUri(ushort const *,ushort *)
0x18001248e  mov     ebx, eax
0x180012490  mov     [rsp+2A8h+var_268], eax
0x180012494  test    eax, eax
0x180012496  jns     short loc_18001249A
0x180012498  jmp     short loc_1800124EA
0x18001249a  lea     rdx, [rsp+2A8h+var_260]
0x18001249f  call    ?GetSession@CompatibilityAdapter@@QEBA?AV?$AutoRef@VRpcSession@@@wmi@@XZ; CompatibilityAdapter::GetSession(void)
0x1800124a4  nop
0x1800124a5  xorps   xmm0, xmm0
0x1800124a8  movups  xmmword ptr [rsp+2A8h+var_238.Data1], xmm0
0x1800124ad  lea     rax, [rsp+2A8h+var_238]
0x1800124b2  mov     [rsp+2A8h+var_270], rax; struct _GUID *
0x1800124b7  lea     rdx, [rsp+2A8h+var_228]; unsigned __int16 *
0x1800124bf  mov     rcx, [rsp+2A8h+var_260]; this
0x1800124c4  call    ?RunTask@RpcSession@@QEBAJPEBGKPEAPEBGKK0PEAU_GUID@@@Z; RpcSession::RunTask(ushort const *,ulong,ushort const * *,ulong,ulong,ushort const *,_GUID *)
0x1800124c9  mov     ebx, eax
0x1800124cb  mov     [rsp+2A8h+var_268], eax
0x1800124cf  mov     rcx, [rsp+2A8h+var_260]; this
0x1800124d4  test    rcx, rcx
0x1800124d7  jz      short loc_1800124DF
0x1800124d9  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x1800124de  nop
0x1800124df  jmp     short loc_1800124EA
0x1800124e1  mov     ebx, [rsp+2A8h+var_268]
0x1800124e5  mov     rdi, [rsp+2A8h+var_250]
0x1800124ea  mov     eax, [rdi+58h]
0x1800124ed  test    ebx, ebx
0x1800124ef  js      short loc_18001250B
0x1800124f1  mov     dword ptr [rdi+0C0h], 0
0x1800124fb  movups  xmm0, xmmword ptr [rsp+2A8h+SystemTime.wYear]
0x180012500  movdqu  xmmword ptr [rdi+60h], xmm0
0x180012505  btr     eax, 13h
0x180012509  jmp     short loc_180012515
0x18001250b  mov     [rdi+0C0h], ebx
0x180012511  bts     eax, 13h
0x180012515  and     eax, 0FBFF7FFFh
0x18001251a  bts     eax, 1Dh
0x18001251e  mov     [rdi+58h], eax
0x180012521  mov     r9d, 5; unsigned int
0x180012527  xor     r8d, r8d; int
0x18001252a  xor     edx, edx; lpFileName
0x18001252c  mov     rcx, rdi; this
0x18001252f  call    ?SaveWithRetry@CJob@@QEAAJPEBGHK@Z; CJob::SaveWithRetry(ushort const *,int,ulong)
0x180012534  mov     rcx, [rsp+2A8h+var_18]
0x18001253c  xor     rcx, rsp; StackCookie
0x18001253f  call    __security_check_cookie
0x180012544  mov     rbx, [rsp+2A8h+arg_0]
0x18001254c  add     rsp, 2A0h
0x180012553  pop     rdi
0x180012554  retn
```
