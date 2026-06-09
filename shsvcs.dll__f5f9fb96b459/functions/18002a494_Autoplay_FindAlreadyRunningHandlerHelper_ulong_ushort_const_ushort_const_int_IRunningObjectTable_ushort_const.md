# Autoplay::_FindAlreadyRunningHandlerHelper(ulong,ushort const *,ushort const *,int *,IRunningObjectTable *,ushort const *)

- ea: `0x18002a494`
- end: `0x18002a5bf`
- name: `?_FindAlreadyRunningHandlerHelper@Autoplay@@YAJKPEBG0PEAHPEAUIRunningObjectTable@@0@Z`
- size: `299`
- prototype: `__int64 __fastcall(Autoplay *this, struct IHWEventHandler *, struct _GUID *, HKEY *, int *, struct IRunningObjectTable *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800056c8`

## callees

- `0x18001c360`
- `0x18002a494`
- `0x18002a650`
- `0x18002e9b8`
- `0x180032c90`
- `0x180034010`

## import_xrefs

- `ntdll!RtlGetActiveConsoleId` at `0x18002a4ed`
- `ntdll!RtlGetActiveConsoleId` at `0x18002a4ed`

## pseudocode

```c
__int64 __fastcall Autoplay::_FindAlreadyRunningHandlerHelper(
        Autoplay *this,
        struct IHWEventHandler *a2,
        struct _GUID *a3,
        HKEY *a4,
        int *a5,
        struct IRunningObjectTable *a6)
{
  unsigned int ActiveConsoleId; // edi
  const unsigned __int16 *v10; // rcx
  int HandlerCancelCLSID; // ebx
  __int64 v12; // rax
  struct IHWEventHandler *v14; // [rsp+20h] [rbp-30h] BYREF
  __int64 v15; // [rsp+28h] [rbp-28h] BYREF
  struct IMoniker *v16; // [rsp+30h] [rbp-20h] BYREF
  struct _GUID v17; // [rsp+38h] [rbp-18h] BYREF

  ActiveConsoleId = (unsigned int)this;
  v17 = 0;
  HandlerCancelCLSID = Settings::GetHandlerCancelCLSID((const wchar_t *)a6, (unsigned __int16 *)&v17, a3, a4);
  if ( HandlerCancelCLSID >= 0 )
  {
    v16 = 0;
    if ( !ActiveConsoleId )
      ActiveConsoleId = RtlGetActiveConsoleId();
    HandlerCancelCLSID = _BuildMoniker(v10, &v17, ActiveConsoleId, &v16);
    if ( HandlerCancelCLSID >= 0 )
    {
      v12 = *(_QWORD *)a5;
      v15 = 0;
      if ( (*(int (__fastcall **)(int *, struct IMoniker *, __int64 *))(v12 + 48))(a5, v16, &v15) < 0 )
      {
        HandlerCancelCLSID = 0;
      }
      else
      {
        v14 = 0;
        HandlerCancelCLSID = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IHWEventHandler **))v15)(
                               v15,
                               &GUID_c1fb73d0_ec3a_4ba2_b512_8cdb9187b6d1,
                               &v14);
        if ( HandlerCancelCLSID >= 0 )
        {
          HandlerCancelCLSID = Autoplay::_QueryRunningObject(
                                 v14,
                                 a2,
                                 (const unsigned __int16 *)a3,
                                 (const unsigned __int16 *)a4,
                                 (int *)v14);
          ((void (__fastcall *)(struct IHWEventHandler *))v14->lpVtbl->Release)(v14);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      ((void (__fastcall *)(struct IMoniker *))v16->lpVtbl->Release)(v16);
    }
  }
  return (unsigned int)HandlerCancelCLSID;
}

```

## disassembly

```asm
0x18002a494  push    rbp
0x18002a496  push    rbx
0x18002a497  push    rsi
0x18002a498  push    rdi
0x18002a499  push    r12
0x18002a49b  push    r14
0x18002a49d  push    r15
0x18002a49f  mov     rbp, rsp
0x18002a4a2  sub     rsp, 50h
0x18002a4a6  mov     rax, cs:__security_cookie
0x18002a4ad  xor     rax, rsp
0x18002a4b0  mov     [rbp+var_8], rax
0x18002a4b4  mov     rsi, [rbp+arg_20]
0x18002a4b8  mov     r14, rdx
0x18002a4bb  mov     edi, ecx
0x18002a4bd  lea     rdx, [rbp+var_18]; unsigned __int16 *
0x18002a4c1  mov     rcx, [rbp+arg_28]; this
0x18002a4c5  xorps   xmm0, xmm0
0x18002a4c8  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x18002a4cc  mov     r12, r9
0x18002a4cf  mov     r15, r8
0x18002a4d2  call    ?GetHandlerCancelCLSID@Settings@@YAJPEBGPEAU_GUID@@@Z; Settings::GetHandlerCancelCLSID(ushort const *,_GUID *)
0x18002a4d7  mov     ebx, eax
0x18002a4d9  test    eax, eax
0x18002a4db  js      loc_18002A5A2
0x18002a4e1  mov     [rbp+var_20], 0
0x18002a4e9  test    edi, edi
0x18002a4eb  jnz     short loc_18002A4F5
0x18002a4ed  call    cs:__imp_RtlGetActiveConsoleId
0x18002a4f3  mov     edi, eax
0x18002a4f5  lea     r9, [rbp+var_20]; struct IMoniker **
0x18002a4f9  mov     r8d, edi; unsigned int
0x18002a4fc  lea     rdx, [rbp+var_18]; struct _GUID *
0x18002a500  call    ?_BuildMoniker@@YAJPEBGAEBU_GUID@@KPEAPEAUIMoniker@@@Z; _BuildMoniker(ushort const *,_GUID const &,ulong,IMoniker * *)
0x18002a505  mov     ebx, eax
0x18002a507  test    eax, eax
0x18002a509  js      loc_18002A5A2
0x18002a50f  mov     rax, [rsi]
0x18002a512  lea     r8, [rbp+var_28]
0x18002a516  mov     rdx, [rbp+var_20]
0x18002a51a  mov     rcx, rsi
0x18002a51d  mov     [rbp+var_28], 0
0x18002a525  mov     rax, [rax+30h]
0x18002a529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a52e  test    eax, eax
0x18002a530  js      short loc_18002A590
0x18002a532  mov     rcx, [rbp+var_28]
0x18002a536  lea     r8, [rbp+var_30]
0x18002a53a  mov     [rbp+var_30], 0
0x18002a542  lea     rdx, _GUID_c1fb73d0_ec3a_4ba2_b512_8cdb9187b6d1
0x18002a549  mov     rax, [rcx]
0x18002a54c  mov     rax, [rax]
0x18002a54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a554  mov     ebx, eax
0x18002a556  test    eax, eax
0x18002a558  js      short loc_18002A57E
0x18002a55a  mov     rcx, [rbp+var_30]; this
0x18002a55e  mov     r9, r12; unsigned __int16 *
0x18002a561  mov     r8, r15; unsigned __int16 *
0x18002a564  mov     rdx, r14; struct IHWEventHandler *
0x18002a567  call    ?_QueryRunningObject@Autoplay@@YAJPEAUIHWEventHandler@@PEBG1PEAH@Z; Autoplay::_QueryRunningObject(IHWEventHandler *,ushort const *,ushort const *,int *)
0x18002a56c  mov     rcx, [rbp+var_30]
0x18002a570  mov     ebx, eax
0x18002a572  mov     rax, [rcx]
0x18002a575  mov     rax, [rax+10h]
0x18002a579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a57e  mov     rcx, [rbp+var_28]
0x18002a582  mov     rax, [rcx]
0x18002a585  mov     rax, [rax+10h]
0x18002a589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a58e  jmp     short loc_18002A592
0x18002a590  xor     ebx, ebx
0x18002a592  mov     rcx, [rbp+var_20]
0x18002a596  mov     rax, [rcx]
0x18002a599  mov     rax, [rax+10h]
0x18002a59d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5a2  mov     eax, ebx
0x18002a5a4  mov     rcx, [rbp+var_8]
0x18002a5a8  xor     rcx, rsp; StackCookie
0x18002a5ab  call    __security_check_cookie
0x18002a5b0  add     rsp, 50h
0x18002a5b4  pop     r15
0x18002a5b6  pop     r14
0x18002a5b8  pop     r12
0x18002a5ba  pop     rdi
0x18002a5bb  pop     rsi
0x18002a5bc  pop     rbx
0x18002a5bd  pop     rbp
0x18002a5be  retn
```
