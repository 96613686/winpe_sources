# GetShareInfoAndCheckAccess(wchar_t const *,wchar_t const *,_SHARE_INFO_502 * *)

- ea: `0x1801ba16c`
- end: `0x1801ba279`
- name: `?GetShareInfoAndCheckAccess@@YA_NPEB_W0PEAPEAU_SHARE_INFO_502@@@Z`
- size: `269`
- prototype: `bool __fastcall(LPWSTR servername, LPWSTR netname, struct _SHARE_INFO_502 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180178de4`
- `0x180205370`

## callees

- `0x1800983c0`
- `0x1800f4820`
- `0x180147154`
- `0x1801a40bc`
- `0x1801ba108`
- `0x1801ba16c`
- `0x1801ba2f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801ba1a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801ba1a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801ba1b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801ba1b5`
- `srvcli!NetShareGetInfo` at `0x1801ba1f1`
- `srvcli!NetShareGetInfo` at `0x1801ba1f1`
- `netutils!NetApiBufferFree` at `0x1801ba253`
- `netutils!NetApiBufferFree` at `0x1801ba253`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall GetShareInfoAndCheckAccess(LPWSTR servername, LPWSTR netname, LPBYTE *a3)
{
  void **v6; // rbx
  HANDLE CurrentThread; // rax
  void *v8; // rdx
  const char *v9; // r9
  DWORD Info; // ebx
  LPBYTE v11; // rcx
  const wchar_t *v12; // rdx
  __int64 v13; // rax
  char v14; // bl
  _BYTE v16[40]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPBYTE bufptr; // [rsp+60h] [rbp+18h] BYREF
  void *v19; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  bufptr = 0;
  v19 = 0;
  v6 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v19);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, v6) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x706,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\secutil.cxx",
      v9);
  CRevertToSelf::CRevertToSelf((CRevertToSelf *)v16, v8);
  Info = NetShareGetInfo(servername, netname, 0x1F6u, &bufptr);
  CRevertToSelf::~CRevertToSelf((CRevertToSelf *)v16);
  if ( Info )
  {
LABEL_10:
    v11 = bufptr;
    goto LABEL_11;
  }
  v11 = bufptr;
  v12 = (const wchar_t *)*((_QWORD *)bufptr + 5);
  if ( v12 )
  {
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    if ( v13 )
    {
      if ( ShareAccessCheck(*((void *const *)bufptr + 8), v12, v19) )
      {
        *a3 = bufptr;
        v14 = 1;
        goto LABEL_13;
      }
      goto LABEL_10;
    }
  }
LABEL_11:
  v14 = 0;
  if ( v11 )
    NetApiBufferFree(v11);
LABEL_13:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
  return v14;
}

```

## disassembly

```asm
0x1801ba16c  mov     rax, rsp
0x1801ba16f  mov     [rax+8], rbx
0x1801ba173  mov     [rax+10h], rbp
0x1801ba177  push    rsi
0x1801ba178  push    rdi
0x1801ba179  push    r14
0x1801ba17b  sub     rsp, 30h
0x1801ba17f  mov     rdi, r8
0x1801ba182  mov     rsi, rdx
0x1801ba185  mov     rbp, rcx
0x1801ba188  xor     r14d, r14d
0x1801ba18b  mov     [r8], r14
0x1801ba18e  mov     [rax+18h], r14
0x1801ba192  mov     [rax+20h], r14
0x1801ba196  lea     rcx, [rax+20h]
0x1801ba19a  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1801ba19f  mov     rbx, rax
0x1801ba1a2  call    cs:__imp_GetCurrentThread
0x1801ba1a8  mov     r9, rbx; TokenHandle
0x1801ba1ab  xor     r8d, r8d; OpenAsSelf
0x1801ba1ae  lea     edx, [r14+8]; DesiredAccess
0x1801ba1b2  mov     rcx, rax; ThreadHandle
0x1801ba1b5  call    cs:__imp_OpenThreadToken
0x1801ba1bb  test    eax, eax
0x1801ba1bd  jnz     short loc_1801BA1D6
0x1801ba1bf  mov     rcx, [rsp+48h]; this
0x1801ba1c4  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1801ba1cb  mov     edx, 706h; void *
0x1801ba1d0  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801ba1d6  lea     rcx, [rsp+48h+var_28]; this
0x1801ba1db  call    ??0CRevertToSelf@@QEAA@PEAX@Z; CRevertToSelf::CRevertToSelf(void *)
0x1801ba1e0  lea     r9, [rsp+48h+bufptr]; bufptr
0x1801ba1e5  mov     r8d, 1F6h; level
0x1801ba1eb  mov     rdx, rsi; netname
0x1801ba1ee  mov     rcx, rbp; servername
0x1801ba1f1  call    cs:__imp_NetShareGetInfo
0x1801ba1f7  mov     ebx, eax
0x1801ba1f9  lea     rcx, [rsp+48h+var_28]; this
0x1801ba1fe  call    ??1CRevertToSelf@@QEAA@XZ; CRevertToSelf::~CRevertToSelf(void)
0x1801ba203  test    ebx, ebx
0x1801ba205  jnz     short loc_1801BA246
0x1801ba207  mov     rcx, [rsp+48h+bufptr]
0x1801ba20c  mov     rdx, [rcx+28h]; wchar_t *
0x1801ba210  test    rdx, rdx
0x1801ba213  jz      short loc_1801BA24B
0x1801ba215  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801ba219  inc     rax
0x1801ba21c  cmp     [rdx+rax*2], r14w
0x1801ba221  jnz     short loc_1801BA219
0x1801ba223  test    rax, rax
0x1801ba226  jz      short loc_1801BA24B
0x1801ba228  mov     r8, [rsp+48h+arg_18]; void *
0x1801ba22d  mov     rcx, [rcx+40h]; void *
0x1801ba231  call    ?ShareAccessCheck@@YA_NQEAXPEB_WPEAX@Z; ShareAccessCheck(void * const,wchar_t const *,void *)
0x1801ba236  test    al, al
0x1801ba238  jz      short loc_1801BA246
0x1801ba23a  mov     rax, [rsp+48h+bufptr]
0x1801ba23f  mov     [rdi], rax
0x1801ba242  mov     bl, 1
0x1801ba244  jmp     short loc_1801BA25A
0x1801ba246  mov     rcx, [rsp+48h+bufptr]; Buffer
0x1801ba24b  mov     bl, r14b
0x1801ba24e  test    rcx, rcx
0x1801ba251  jz      short loc_1801BA25A
0x1801ba253  call    cs:__imp_NetApiBufferFree
0x1801ba259  nop
0x1801ba25a  lea     rcx, [rsp+48h+arg_18]
0x1801ba25f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801ba264  mov     al, bl
0x1801ba266  mov     rbx, [rsp+48h+arg_0]
0x1801ba26b  mov     rbp, [rsp+48h+arg_8]
0x1801ba270  add     rsp, 30h
0x1801ba274  pop     r14
0x1801ba276  pop     rdi
0x1801ba277  pop     rsi
0x1801ba278  retn
```
