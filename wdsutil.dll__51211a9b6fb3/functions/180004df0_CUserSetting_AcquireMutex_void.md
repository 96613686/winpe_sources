# CUserSetting::AcquireMutex(void)

- ea: `0x180004df0`
- end: `0x180004ea3`
- name: `?AcquireMutex@CUserSetting@@IEAAXXZ`
- size: `179`
- prototype: `void __fastcall(CUserSetting *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180004eb0`
- `0x1800051e0`
- `0x180005570`
- `0x180005f90`

## callees

- `0x180004df0`
- `0x18000892c`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x180004e18`
- `KERNEL32!CreateMutexW` at `0x180004e18`
- `KERNEL32!WaitForSingleObject` at `0x180004e5f`
- `KERNEL32!WaitForSingleObject` at `0x180004e5f`
- `WDSCORE!CurrentIP` at `0x180004e2d`
- `WDSCORE!CurrentIP` at `0x180004e6f`
- `WDSCORE!CurrentIP` at `0x180004e2d`
- `WDSCORE!CurrentIP` at `0x180004e6f`

## pseudocode

```c
void __fastcall CUserSetting::AcquireMutex(CUserSetting *this)
{
  HANDLE MutexW; // rax
  void *v3; // rax
  unsigned int v4; // ecx
  const unsigned __int16 *v5; // r9
  void *v6; // rax
  unsigned int v7; // ecx
  const unsigned __int16 *v8; // r9

  MutexW = (HANDLE)*((_QWORD *)this + 1);
  if ( !MutexW )
  {
    MutexW = CreateMutexW(0, 0, L"Setup.UserSetting.Mutex");
    *((_QWORD *)this + 1) = MutexW;
    if ( !MutexW )
    {
      v3 = (void *)CurrentIP();
      Ui_Assert(v4, "_hMutex != 0", 0x4Du, v5, L"CUserSetting::AcquireMutex", v3);
      MutexW = (HANDLE)*((_QWORD *)this + 1);
    }
  }
  if ( WaitForSingleObject(MutexW, 0xFFFFFFFF) )
  {
    v6 = (void *)CurrentIP();
    Ui_Assert(v7, "dwResult == ((((DWORD )0x00000000L) ) + 0 )", 0x50u, v8, L"CUserSetting::AcquireMutex", v6);
  }
}

```

## disassembly

```asm
0x180004df0  mov     [rsp+arg_0], rbx
0x180004df5  push    rdi
0x180004df6  sub     rsp, 30h
0x180004dfa  mov     rax, [rcx+8]
0x180004dfe  lea     rdi, aCusersettingAc; "CUserSetting::AcquireMutex"
0x180004e05  mov     rbx, rcx
0x180004e08  test    rax, rax
0x180004e0b  jnz     short loc_180004E59
0x180004e0d  lea     r8, Name; "Setup.UserSetting.Mutex"
0x180004e14  xor     edx, edx; bInitialOwner
0x180004e16  xor     ecx, ecx; lpMutexAttributes
0x180004e18  call    cs:__imp_CreateMutexW
0x180004e1f  nop     dword ptr [rax+rax+00h]
0x180004e24  mov     [rbx+8], rax
0x180004e28  test    rax, rax
0x180004e2b  jnz     short loc_180004E59
0x180004e2d  call    cs:__imp_CurrentIP
0x180004e34  nop     dword ptr [rax+rax+00h]
0x180004e39  mov     [rsp+38h+var_10], rax; void *
0x180004e3e  mov     r8d, 4Dh ; 'M'; unsigned int
0x180004e44  lea     rdx, aHmutex0; "_hMutex != 0"
0x180004e4b  mov     [rsp+38h+var_18], rdi; unsigned __int16 *
0x180004e50  call    ?Ui_Assert@@YAXKPEBDKPEBG1PEAX@Z; Ui_Assert(ulong,char const *,ulong,ushort const *,ushort const *,void *)
0x180004e55  mov     rax, [rbx+8]
0x180004e59  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004e5c  mov     rcx, rax; hHandle
0x180004e5f  call    cs:__imp_WaitForSingleObject
0x180004e66  nop     dword ptr [rax+rax+00h]
0x180004e6b  test    eax, eax
0x180004e6d  jz      short loc_180004E97
0x180004e6f  call    cs:__imp_CurrentIP
0x180004e76  nop     dword ptr [rax+rax+00h]
0x180004e7b  mov     [rsp+38h+var_10], rax; void *
0x180004e80  mov     r8d, 50h ; 'P'; unsigned int
0x180004e86  lea     rdx, aDwresultDword0; "dwResult == ((((DWORD )0x00000000L) ) +"...
0x180004e8d  mov     [rsp+38h+var_18], rdi; unsigned __int16 *
0x180004e92  call    ?Ui_Assert@@YAXKPEBDKPEBG1PEAX@Z; Ui_Assert(ulong,char const *,ulong,ushort const *,ushort const *,void *)
0x180004e97  mov     rbx, [rsp+38h+arg_0]
0x180004e9c  add     rsp, 30h
0x180004ea0  pop     rdi
0x180004ea1  retn
```
