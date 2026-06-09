# DBManager::MountDeviceVolume(ushort const *,int)

- ea: `0x180016f9c`
- end: `0x180017132`
- name: `?MountDeviceVolume@DBManager@@IEAAJPEBGH@Z`
- size: `406`
- prototype: `int(DBManager *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800189b4`

## callees

- `0x1800068f0`
- `0x180016f9c`
- `0x180017138`
- `0x1800396c8`
- `0x180039898`
- `0x18003bf70`
- `0x1800c50f0`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017098`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180016fd3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180016fd3`

## string_xrefs

- `0x180016ffa`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800170c6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
int __fastcall DBManager::MountDeviceVolume(DBManager *this, const unsigned __int16 *a2, int a3)
{
  struct IUnknown **v3; // rdi
  unsigned int v7; // edx
  int VolumePath; // eax
  int v9; // ebx
  int result; // eax
  __int64 v11; // rax
  int v12; // eax
  struct IUnknown *v13; // rcx
  void *v14; // rax
  int v15; // [rsp+30h] [rbp-248h] BYREF
  struct IUnknown *v16; // [rsp+38h] [rbp-240h] BYREF
  unsigned __int16 v17[264]; // [rsp+40h] [rbp-238h] BYREF

  v3 = (struct IUnknown **)((char *)this + 56);
  if ( *((_QWORD *)this + 7) )
    return 0;
  if ( PathFileExistsW(a2) )
  {
    VolumePath = DBManager::GetVolumePath(v17, v7, a2);
    v9 = VolumePath;
    if ( VolumePath < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)VolumePath,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        1122);
      return v9;
    }
    v11 = *(_QWORD *)this;
    v16 = 0;
    v12 = (*(__int64 (__fastcall **)(DBManager *, unsigned __int16 *, _QWORD, struct IUnknown **))(v11 + 80))(
            this,
            v17,
            a3 != 0 ? 5 : 3,
            &v16);
    v9 = v12;
    if ( v12 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v12,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        1126);
      if ( v16 )
        ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
      return v9;
    }
    v13 = v16;
    if ( *v3 != v16 )
    {
      ATL::AtlComPtrAssign(v3, v16);
      v13 = v16;
    }
    if ( v13 )
      ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->Release)(v13);
    return 0;
  }
  result = GetLastError();
  v15 = result;
  if ( (Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits & 0x20) != 0 )
  {
    v14 = _t_address();
    EtwTraceMessage(&ETWMESSAGE, v14, &v15, 4, 0, -1);
    result = v15;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180016f9c  mov     [rsp+arg_10], rbx
0x180016fa1  push    rbp
0x180016fa2  push    rsi
0x180016fa3  push    rdi
0x180016fa4  sub     rsp, 260h
0x180016fab  mov     rax, cs:__security_cookie
0x180016fb2  xor     rax, rsp
0x180016fb5  mov     [rsp+278h+var_28], rax
0x180016fbd  lea     rdi, [rcx+38h]
0x180016fc1  mov     ebp, r8d
0x180016fc4  cmp     qword ptr [rdi], 0
0x180016fc8  mov     rbx, rdx
0x180016fcb  mov     rsi, rcx
0x180016fce  jnz     short loc_180017043
0x180016fd0  mov     rcx, rdx; pszPath
0x180016fd3  call    cs:__imp_PathFileExistsW
0x180016fd9  test    eax, eax
0x180016fdb  jz      loc_180017098
0x180016fe1  mov     r8, rbx; unsigned __int16 *
0x180016fe4  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x180016fe9  call    ?GetVolumePath@DBManager@@SAJPEAGKPEBG@Z; DBManager::GetVolumePath(ushort *,ulong,ushort const *)
0x180016fee  mov     ebx, eax
0x180016ff0  test    eax, eax
0x180016ff2  jns     short loc_180017047
0x180016ff4  mov     r9d, 462h
0x180016ffa  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180017001  mov     edx, 1
0x180017006  mov     ecx, eax
0x180017008  call    Log_UnistoreHREvent_0
0x18001700d  mov     eax, ebx
0x18001700f  mov     rcx, [rsp+278h+var_28]
0x180017017  xor     rcx, rsp; StackCookie
0x18001701a  call    __security_check_cookie
0x18001701f  mov     rbx, [rsp+278h+arg_10]
0x180017027  add     rsp, 260h
0x18001702e  pop     rdi
0x18001702f  pop     rsi
0x180017030  pop     rbp
0x180017031  retn
0x180017032  test    rcx, rcx
0x180017035  jz      short loc_180017043
0x180017037  mov     rax, [rcx]
0x18001703a  mov     rax, [rax+10h]
0x18001703e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017043  xor     eax, eax
0x180017045  jmp     short loc_18001700F
0x180017047  mov     rax, [rsi]
0x18001704a  lea     r9, [rsp+278h+var_240]
0x18001704f  neg     ebp
0x180017051  mov     [rsp+278h+var_240], 0
0x18001705a  lea     rdx, [rsp+278h+var_238]
0x18001705f  mov     rcx, rsi
0x180017062  sbb     r8d, r8d
0x180017065  mov     rax, [rax+50h]
0x180017069  and     r8d, 2
0x18001706d  add     r8d, 3
0x180017071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017076  mov     ebx, eax
0x180017078  test    eax, eax
0x18001707a  js      short loc_1800170C0
0x18001707c  mov     rcx, [rsp+278h+var_240]
0x180017081  cmp     [rdi], rcx
0x180017084  jz      short loc_180017032
0x180017086  mov     rdx, rcx; struct IUnknown *
0x180017089  mov     rcx, rdi; struct IUnknown **
0x18001708c  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180017091  mov     rcx, [rsp+278h+var_240]
0x180017096  jmp     short loc_180017032
0x180017098  call    cs:__imp_GetLastError
0x18001709e  test    byte ptr cs:Microsoft_Windows_UserDataAccess_UnifiedStoreEnableBits, 20h
0x1800170a5  mov     [rsp+278h+var_248], eax
0x1800170a9  jnz     short loc_1800170F8
0x1800170ab  test    eax, eax
0x1800170ad  jle     loc_18001700F
0x1800170b3  movzx   eax, ax
0x1800170b6  or      eax, 80070000h
0x1800170bb  jmp     loc_18001700F
0x1800170c0  mov     r9d, 466h
0x1800170c6  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800170cd  mov     edx, 1
0x1800170d2  mov     ecx, ebx
0x1800170d4  call    Log_UnistoreHREvent_0
0x1800170d9  mov     rcx, [rsp+278h+var_240]
0x1800170de  test    rcx, rcx
0x1800170e1  jz      loc_18001700D
0x1800170e7  mov     rax, [rcx]
0x1800170ea  mov     rax, [rax+10h]
0x1800170ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170f3  jmp     loc_18001700D
0x1800170f8  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x1800170fd  mov     rdx, rax; void *
0x180017100  mov     [rsp+278h+var_250], 0FFFFFFFFFFFFFFFFh
0x180017109  mov     r9d, 4
0x18001710f  mov     [rsp+278h+var_258], 0
0x180017118  lea     r8, [rsp+278h+var_248]
0x18001711d  lea     rcx, _ETWMESSAGE; EventDescriptor
0x180017124  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x180017129  mov     eax, [rsp+278h+var_248]
0x18001712d  jmp     loc_1800170AB
```
