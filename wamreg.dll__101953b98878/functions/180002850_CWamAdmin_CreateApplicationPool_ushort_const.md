# CWamAdmin::CreateApplicationPool(ushort const *)

- ea: `0x180002850`
- end: `0x180002926`
- name: `?CreateApplicationPool@CWamAdmin@@UEAAJPEBG@Z`
- size: `214`
- prototype: `__int64 __fastcall(CWamAdmin *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001d2c`
- `0x180002850`
- `0x180003cdc`
- `0x180005738`
- `0x1800061d0`
- `0x180006822`
- `0x180006850`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800028b7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800028cb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800028b7`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800028cb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800028fd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800028fd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002894`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002894`

## pseudocode

```c
__int64 __fastcall CWamAdmin::CreateApplicationPool(CWamAdmin *this, const unsigned __int16 *a2)
{
  WamRegGlobal *v3; // rcx
  WamRegMetabaseConfig *v4; // rcx
  int v5; // ebx
  struct IMSAdminBaseW *v6; // rdx
  struct IMSAdminBaseW *v7; // rdx
  const unsigned __int16 *v8; // r9
  _BYTE v10[32]; // [rsp+20h] [rbp-D8h] BYREF
  unsigned __int16 *v11; // [rsp+40h] [rbp-B8h]
  unsigned __int16 v12[64]; // [rsp+60h] [rbp-98h] BYREF

  memset_0(v12, 0, sizeof(v12));
  STRU::STRU((STRU *)v10, v12, 0x40u);
  WamRegGlobal::AcquireAdmWriteLock(v3);
  if ( a2 )
  {
    v5 = STRU::Append((STRU *)v10, L"/LM/W3SVC/AppPools/");
    if ( v5 >= 0 )
    {
      v5 = STRU::Append((STRU *)v10, a2);
      if ( v5 >= 0 )
      {
        v5 = WamRegMetabaseConfig::MDCreatePath(v4, v6, v11);
        if ( v5 >= 0 )
          v5 = WamRegMetabaseConfig::MDSetKeyType(v4, v7, v11, v8);
      }
    }
  }
  else
  {
    v5 = -2147024809;
  }
  WamRegGlobal::ReleaseAdmWriteLock(v4);
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002850  mov     [rsp+arg_0], rbx
0x180002855  push    rdi
0x180002856  sub     rsp, 0F0h
0x18000285d  mov     rax, cs:__security_cookie
0x180002864  xor     rax, rsp
0x180002867  mov     [rsp+0F8h+var_18], rax
0x18000286f  mov     rdi, rdx
0x180002872  lea     rcx, [rsp+0F8h+var_98]; void *
0x180002877  xor     edx, edx; Val
0x180002879  mov     r8d, 80h; Size
0x18000287f  call    memset_0
0x180002884  mov     r8d, 40h ; '@'
0x18000288a  lea     rdx, [rsp+0F8h+var_98]
0x18000288f  lea     rcx, [rsp+0F8h+var_D8]
0x180002894  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000289a  call    ?AcquireAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::AcquireAdmWriteLock(void)
0x18000289f  test    rdi, rdi
0x1800028a2  jnz     short loc_1800028AB
0x1800028a4  mov     ebx, 80070057h
0x1800028a9  jmp     short loc_1800028F3
0x1800028ab  lea     rdx, aLmW3svcApppool; "/LM/W3SVC/AppPools/"
0x1800028b2  lea     rcx, [rsp+0F8h+var_D8]
0x1800028b7  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800028bd  mov     ebx, eax
0x1800028bf  test    eax, eax
0x1800028c1  js      short loc_1800028F3
0x1800028c3  mov     rdx, rdi
0x1800028c6  lea     rcx, [rsp+0F8h+var_D8]
0x1800028cb  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800028d1  mov     ebx, eax
0x1800028d3  test    eax, eax
0x1800028d5  js      short loc_1800028F3
0x1800028d7  mov     r8, [rsp+0F8h+var_B8]; unsigned __int16 *
0x1800028dc  call    ?MDCreatePath@WamRegMetabaseConfig@@QEAAJPEAUIMSAdminBaseW@@PEBG@Z; WamRegMetabaseConfig::MDCreatePath(IMSAdminBaseW *,ushort const *)
0x1800028e1  mov     ebx, eax
0x1800028e3  test    eax, eax
0x1800028e5  js      short loc_1800028F3
0x1800028e7  mov     r8, [rsp+0F8h+var_B8]; unsigned __int16 *
0x1800028ec  call    ?MDSetKeyType@WamRegMetabaseConfig@@QEAAJPEAUIMSAdminBaseW@@PEBG1@Z; WamRegMetabaseConfig::MDSetKeyType(IMSAdminBaseW *,ushort const *,ushort const *)
0x1800028f1  mov     ebx, eax
0x1800028f3  call    ?ReleaseAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::ReleaseAdmWriteLock(void)
0x1800028f8  lea     rcx, [rsp+0F8h+var_D8]
0x1800028fd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002903  mov     eax, ebx
0x180002905  mov     rcx, [rsp+0F8h+var_18]
0x18000290d  xor     rcx, rsp; StackCookie
0x180002910  call    __security_check_cookie
0x180002915  mov     rbx, [rsp+0F8h+arg_0]
0x18000291d  add     rsp, 0F0h
0x180002924  pop     rdi
0x180002925  retn
```
