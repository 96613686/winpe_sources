# CWamAdmin::AppCreate2(ushort const *,ulong)

- ea: `0x180001ed0`
- end: `0x180002097`
- name: `?AppCreate2@CWamAdmin@@UEAAJPEBGK@Z`
- size: `455`
- prototype: `__int64 __fastcall(CWamAdmin *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callees

- `0x180001084`
- `0x180001d2c`
- `0x180001ed0`
- `0x180003cdc`
- `0x180004948`
- `0x180004acc`
- `0x180005738`
- `0x180005a50`
- `0x180007010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180001ff2`
- `iisutil!PuDbgPrint` at `0x180002048`
- `iisutil!PuDbgPrint` at `0x180001ff2`
- `iisutil!PuDbgPrint` at `0x180002048`

## string_xrefs

- `0x180001f7c`: `Failed to create metabase path %S, hr = %08x`
- `0x180001fc9`: `CWamAdmin::AppCreate2`
- `0x180002030`: `CWamAdmin::AppCreate2`
- `0x180002079`: `Failed to get DWORD on metabase path %S, hr = %08x`
- `0x180001fdb`: `Failed to delete old application on path %S, hr = 08x\n`
- `0x180002022`: `Failed to create new application on path %S, hr = 08x\n`

## pseudocode

```c
__int64 __fastcall CWamAdmin::AppCreate2(CWamAdmin *this, const unsigned __int16 *a2)
{
  __int64 result; // rax
  __int64 v4; // rax
  WamRegMetabaseConfig *v5; // rcx
  unsigned int v6; // r8d
  int v7; // eax
  struct IMSAdminBaseW *v8; // rdx
  WamRegMetabaseConfig *v9; // rcx
  int PooledApp; // ebx
  int v11; // eax
  int v12; // [rsp+30h] [rbp-18h]
  int v13; // [rsp+30h] [rbp-18h]
  unsigned int v14; // [rsp+58h] [rbp+10h] BYREF
  void *Block; // [rsp+68h] [rbp+20h] BYREF

  v14 = 0;
  Block = 0;
  if ( !a2 )
    return 2147942487LL;
  result = (*(__int64 (__fastcall **)(CWamAdmin *, const unsigned __int16 *, void **))(*(_QWORD *)this + 88LL))(
             this,
             a2,
             &Block);
  if ( (int)result < 0 )
    return result;
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)Block + v4) );
  if ( (unsigned int)v4 <= 0xA )
    return 2147942487LL;
  WamRegGlobal::AcquireAdmWriteLock((WamRegGlobal *)Block);
  v7 = WamRegMetabaseConfig::MDGetDWORD(v5, (const unsigned __int16 *)Block, v6, &v14);
  PooledApp = v7;
  if ( v7 == -2146646015 )
    goto LABEL_16;
  if ( v7 == -2147024893 )
  {
    v11 = WamRegMetabaseConfig::MDCreatePath(v9, v8, (const unsigned __int16 *)Block);
    PooledApp = v11;
    if ( v11 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        v12 = v11;
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
          752,
          "CWamAdmin::AppCreate2",
          "Failed to create metabase path %S, hr = %08x",
          a2,
          v12);
      }
      goto LABEL_19;
    }
LABEL_16:
    PooledApp = WamRegGlobal::CreatePooledApp(v9, (const unsigned __int16 *)Block, 1, 0);
    if ( PooledApp < 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
        809,
        "CWamAdmin::AppCreate2",
        "Failed to create new application on path %S, hr = 08x\n",
        a2);
    goto LABEL_19;
  }
  if ( v7 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v13 = v7;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
        773,
        "CWamAdmin::AppCreate2",
        "Failed to get DWORD on metabase path %S, hr = %08x",
        a2,
        v13);
    }
    goto LABEL_19;
  }
  if ( v14 )
  {
    if ( WamRegGlobal::DeleteApp(v9, (const unsigned __int16 *)Block, 0, 0) < 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm.cpp",
        786,
        "CWamAdmin::AppCreate2",
        "Failed to delete old application on path %S, hr = 08x\n",
        a2);
    goto LABEL_16;
  }
LABEL_19:
  WamRegGlobal::ReleaseAdmWriteLock(v9);
  if ( Block != a2 )
    operator delete(Block);
  return (unsigned int)PooledApp;
}

```

## disassembly

```asm
0x180001ed0  mov     rax, rsp
0x180001ed3  mov     [rax+8], rbx
0x180001ed7  mov     [rax+18h], rsi
0x180001edb  push    rdi
0x180001edc  sub     rsp, 40h
0x180001ee0  xor     esi, esi
0x180001ee2  mov     rdi, rdx
0x180001ee5  mov     [rax+10h], esi
0x180001ee8  mov     [rax+20h], rsi
0x180001eec  test    rdx, rdx
0x180001eef  jz      loc_180002082
0x180001ef5  mov     rax, [rcx]
0x180001ef8  lea     r8, [rsp+48h+Block]
0x180001efd  mov     rax, [rax+58h]
0x180001f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f06  test    eax, eax
0x180001f08  js      loc_180002087
0x180001f0e  mov     rcx, [rsp+48h+Block]; this
0x180001f13  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001f17  inc     rax
0x180001f1a  cmp     [rcx+rax*2], si
0x180001f1e  jnz     short loc_180001F17
0x180001f20  cmp     eax, 0Ah
0x180001f23  jbe     loc_180002082
0x180001f29  call    ?AcquireAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::AcquireAdmWriteLock(void)
0x180001f2e  mov     rdx, [rsp+48h+Block]; unsigned __int16 *
0x180001f33  lea     r9, [rsp+48h+arg_8]; unsigned int *
0x180001f38  call    ?MDGetDWORD@WamRegMetabaseConfig@@QEAAJPEBGKPEAK@Z; WamRegMetabaseConfig::MDGetDWORD(ushort const *,ulong,ulong *)
0x180001f3d  mov     ebx, eax
0x180001f3f  cmp     eax, 800CC801h
0x180001f44  jz      loc_180001FF8
0x180001f4a  cmp     eax, 80070003h
0x180001f4f  jnz     short loc_180001F88
0x180001f51  mov     r8, [rsp+48h+Block]; unsigned __int16 *
0x180001f56  call    ?MDCreatePath@WamRegMetabaseConfig@@QEAAJPEAUIMSAdminBaseW@@PEBG@Z; WamRegMetabaseConfig::MDCreatePath(IMSAdminBaseW *,ushort const *)
0x180001f5b  mov     ebx, eax
0x180001f5d  test    eax, eax
0x180001f5f  jns     loc_180001FF8
0x180001f65  test    byte ptr cs:g_dwDebugFlags, 3
0x180001f6c  jz      loc_18000204E
0x180001f72  mov     [rsp+48h+var_18], eax
0x180001f76  mov     r8d, 2F0h
0x180001f7c  lea     rax, aFailedToCreate_0; "Failed to create metabase path %S, hr ="...
0x180001f83  jmp     loc_180002029
0x180001f88  test    eax, eax
0x180001f8a  js      loc_180002066
0x180001f90  mov     eax, esi
0x180001f92  cmp     [rsp+48h+arg_8], esi
0x180001f96  jz      short loc_180001F9D
0x180001f98  mov     eax, 1
0x180001f9d  test    eax, eax
0x180001f9f  jz      loc_18000204E
0x180001fa5  mov     rdx, [rsp+48h+Block]; unsigned __int16 *
0x180001faa  xor     r9d, r9d; int
0x180001fad  xor     r8d, r8d; int
0x180001fb0  call    ?DeleteApp@WamRegGlobal@@QEAAJPEBGHH@Z; WamRegGlobal::DeleteApp(ushort const *,int,int)
0x180001fb5  test    eax, eax
0x180001fb7  jns     short loc_180001FF8
0x180001fb9  test    byte ptr cs:g_dwDebugFlags, 3
0x180001fc0  jz      short loc_180001FF8
0x180001fc2  mov     rcx, cs:g_pDebug
0x180001fc9  lea     r9, aCwamadminAppcr; "CWamAdmin::AppCreate2"
0x180001fd0  mov     [rsp+48h+var_18], eax
0x180001fd4  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180001fdb  lea     rax, aFailedToDelete_0; "Failed to delete old application on pat"...
0x180001fe2  mov     [rsp+48h+var_20], rdi
0x180001fe7  mov     r8d, 312h
0x180001fed  mov     [rsp+48h+var_28], rax
0x180001ff2  call    cs:__imp_PuDbgPrint
0x180001ff8  mov     rdx, [rsp+48h+Block]; unsigned __int16 *
0x180001ffd  xor     r9d, r9d; int
0x180002000  lea     r8d, [r9+1]; int
0x180002004  call    ?CreatePooledApp@WamRegGlobal@@QEAAJPEBGHH@Z; WamRegGlobal::CreatePooledApp(ushort const *,int,int)
0x180002009  mov     ebx, eax
0x18000200b  test    eax, eax
0x18000200d  jns     short loc_18000204E
0x18000200f  test    byte ptr cs:g_dwDebugFlags, 3
0x180002016  jz      short loc_18000204E
0x180002018  mov     [rsp+48h+var_18], eax
0x18000201c  mov     r8d, 329h
0x180002022  lea     rax, aFailedToCreate_1; "Failed to create new application on pat"...
0x180002029  mov     rcx, cs:g_pDebug
0x180002030  lea     r9, aCwamadminAppcr; "CWamAdmin::AppCreate2"
0x180002037  mov     [rsp+48h+var_20], rdi
0x18000203c  lea     rdx, aInetsrvIisSvcs_2; "inetsrv\\iis\\svcs\\wam\\wamreg\\wamadm"...
0x180002043  mov     [rsp+48h+var_28], rax
0x180002048  call    cs:__imp_PuDbgPrint
0x18000204e  call    ?ReleaseAdmWriteLock@WamRegGlobal@@QEAAXXZ; WamRegGlobal::ReleaseAdmWriteLock(void)
0x180002053  mov     rcx, [rsp+48h+Block]; Block
0x180002058  cmp     rcx, rdi
0x18000205b  jz      short loc_180002062
0x18000205d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002062  mov     eax, ebx
0x180002064  jmp     short loc_180002087
0x180002066  test    byte ptr cs:g_dwDebugFlags, 3
0x18000206d  jz      short loc_18000204E
0x18000206f  mov     [rsp+48h+var_18], eax
0x180002073  mov     r8d, 305h
0x180002079  lea     rax, aFailedToGetDwo; "Failed to get DWORD on metabase path %S"...
0x180002080  jmp     short loc_180002029
0x180002082  mov     eax, 80070057h
0x180002087  mov     rbx, [rsp+48h+arg_0]
0x18000208c  mov     rsi, [rsp+48h+arg_10]
0x180002091  add     rsp, 40h
0x180002095  pop     rdi
0x180002096  retn
```
