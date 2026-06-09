# ManifestProcessor::ProcessChannelLogConfig(AbstractDomElement &,ChannelConfigWriteData &)

- ea: `0x1400182c4`
- end: `0x1400184a3`
- name: `?ProcessChannelLogConfig@ManifestProcessor@@AEAAXAEAVAbstractDomElement@@AEAVChannelConfigWriteData@@@Z`
- size: `479`
- prototype: `void __fastcall(ManifestProcessor *__hidden this, struct AbstractDomElement *, struct ChannelConfigWriteData *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400178bc`

## callees

- `0x140008170`
- `0x1400182c4`
- `0x140022cec`
- `0x14002b2a8`
- `0x14002f6c8`
- `0x140031804`
- `0x140031810`
- `0x140034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018399`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400183c3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140018399`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400183c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1400183b0`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1400183b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ManifestProcessor::ProcessChannelLogConfig(
        ManifestProcessor *this,
        struct AbstractDomElement *a2,
        struct ChannelConfigWriteData *a3)
{
  ManifestProcessor **v4; // rbx
  ManifestProcessor *v5; // rsi
  const wchar_t *v6; // rbx
  __int64 v7; // rsi
  __int64 v8; // rbx
  const char *v9; // r8
  _BYTE v10[8]; // [rsp+20h] [rbp-30h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+28h] [rbp-28h] BYREF
  ManifestProcessor *v12; // [rsp+80h] [rbp+30h] BYREF
  _WORD *v13; // [rsp+88h] [rbp+38h] BYREF
  __int64 v14; // [rsp+98h] [rbp+48h] BYREF

  v12 = this;
  (*(void (__fastcall **)(struct AbstractDomElement *, __int64 *))(*(_QWORD *)a2 + 24LL))(a2, &v14);
  v12 = 0;
  while ( 1 )
  {
    v4 = (ManifestProcessor **)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v14 + 8LL))(v14, v10);
    wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v12);
    v12 = *v4;
    v5 = v12;
    *v4 = 0;
    wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(v10);
    if ( !v5 )
      break;
    v6 = (const wchar_t *)(*(__int64 (__fastcall **)(ManifestProcessor *))(*(_QWORD *)v5 + 16LL))(v5);
    v7 = (*(__int64 (__fastcall **)(ManifestProcessor *))(*(_QWORD *)v5 + 8LL))(v5);
    if ( !wcscmp_0(v6, L"retention") )
    {
      *((_BYTE *)a3 + 224) = ParseXmlBooleanString(v7);
      *((_BYTE *)a3 + 238) |= 1u;
    }
    else if ( !wcscmp_0(v6, L"maxSize") )
    {
      *(_DWORD *)_o__errno() = 0;
      v13 = 0;
      v8 = _o__wcstoui64(v7, &v13, 0);
      if ( *v13 || *(_DWORD *)_o__errno() )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 87);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, v9, 298);
        throw (EvtException *)pExceptionObject;
      }
      *((_QWORD *)a3 + 27) = v8;
      *((_BYTE *)a3 + 240) |= 1u;
    }
    else if ( wcscmp_0(v6, L"filter") && !wcscmp_0(v6, L"autoBackup") )
    {
      *((_BYTE *)a3 + 225) = ParseXmlBooleanString(v7);
      *((_BYTE *)a3 + 239) |= 1u;
    }
  }
  wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v12);
  wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(&v14);
}

```

## disassembly

```asm
0x1400182c4  mov     [rsp-28h+arg_0], rcx
0x1400182c9  push    rbp
0x1400182ca  push    rbx
0x1400182cb  push    rsi
0x1400182cc  push    rdi
0x1400182cd  push    r14
0x1400182cf  mov     rbp, rsp
0x1400182d2  sub     rsp, 50h
0x1400182d6  mov     rdi, r8
0x1400182d9  mov     rcx, rdx
0x1400182dc  mov     rax, [rdx]
0x1400182df  lea     rdx, [rbp+arg_18]
0x1400182e3  mov     rax, [rax+18h]
0x1400182e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400182ec  nop
0x1400182ed  xor     r14d, r14d
0x1400182f0  mov     [rbp+arg_0], r14
0x1400182f4  mov     rcx, [rbp+arg_18]
0x1400182f8  mov     rax, [rcx]
0x1400182fb  lea     rdx, [rbp+var_30]
0x1400182ff  mov     rax, [rax+8]
0x140018303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018308  mov     rbx, rax
0x14001830b  lea     rcx, [rbp+arg_0]
0x14001830f  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x140018314  mov     rsi, [rbx]
0x140018317  mov     [rbp+arg_0], rsi
0x14001831b  mov     [rbx], r14
0x14001831e  test    rsi, rsi
0x140018321  setnz   bl
0x140018324  lea     rcx, [rbp+var_30]
0x140018328  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x14001832d  test    bl, bl
0x14001832f  jz      loc_140018485
0x140018335  mov     rax, [rsi]
0x140018338  mov     rcx, rsi
0x14001833b  mov     rax, [rax+10h]
0x14001833f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018344  mov     rbx, rax
0x140018347  mov     rdx, [rsi]
0x14001834a  mov     rcx, rsi
0x14001834d  mov     rax, [rdx+8]
0x140018351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018356  mov     rsi, rax
0x140018359  lea     rdx, aRetention_0; "retention"
0x140018360  mov     rcx, rbx; String1
0x140018363  call    wcscmp_0
0x140018368  test    eax, eax
0x14001836a  jnz     short loc_140018386
0x14001836c  mov     rcx, rsi
0x14001836f  call    ParseXmlBooleanString
0x140018374  mov     [rdi+0E0h], al
0x14001837a  or      byte ptr [rdi+0EEh], 1
0x140018381  jmp     loc_1400182F4
0x140018386  lea     rdx, aMaxsize; "maxSize"
0x14001838d  mov     rcx, rbx; String1
0x140018390  call    wcscmp_0
0x140018395  test    eax, eax
0x140018397  jnz     short loc_1400183E1
0x140018399  call    cs:__imp__o__errno
0x14001839f  mov     [rax], r14d
0x1400183a2  mov     [rbp+arg_8], r14
0x1400183a6  xor     r8d, r8d
0x1400183a9  lea     rdx, [rbp+arg_8]
0x1400183ad  mov     rcx, rsi
0x1400183b0  call    cs:__imp__o__wcstoui64
0x1400183b6  mov     rbx, rax
0x1400183b9  mov     rcx, [rbp+arg_8]
0x1400183bd  cmp     [rcx], r14w
0x1400183c1  jnz     short loc_140018429
0x1400183c3  call    cs:__imp__o__errno
0x1400183c9  cmp     [rax], r14d
0x1400183cc  jnz     short loc_140018429
0x1400183ce  mov     [rdi+0D8h], rbx
0x1400183d5  or      byte ptr [rdi+0F0h], 1
0x1400183dc  jmp     loc_1400182F4
0x1400183e1  lea     rdx, aFilter; "filter"
0x1400183e8  mov     rcx, rbx; String1
0x1400183eb  call    wcscmp_0
0x1400183f0  test    eax, eax
0x1400183f2  jz      loc_1400182F4
0x1400183f8  lea     rdx, aAutobackup; "autoBackup"
0x1400183ff  mov     rcx, rbx; String1
0x140018402  call    wcscmp_0
0x140018407  test    eax, eax
0x140018409  jnz     loc_1400182F4
0x14001840f  mov     rcx, rsi
0x140018412  call    ParseXmlBooleanString
0x140018417  mov     [rdi+0E1h], al
0x14001841d  or      byte ptr [rdi+0EFh], 1
0x140018424  jmp     loc_1400182F4
0x140018429  lea     rax, WPP_GLOBAL_Control
0x140018430  mov     ebx, 57h ; 'W'
0x140018435  mov     rcx, cs:WPP_GLOBAL_Control
0x14001843c  cmp     rcx, rax
0x14001843f  jz      short loc_140018463
0x140018441  test    byte ptr [rcx+1Ch], 4
0x140018445  jz      short loc_140018463
0x140018447  cmp     byte ptr [rcx+19h], 2
0x14001844b  jb      short loc_140018463
0x14001844d  lea     edx, [rbx-41h]
0x140018450  mov     r9d, ebx
0x140018453  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x14001845a  mov     rcx, [rcx+10h]
0x14001845e  call    WPP_SF_d
0x140018463  mov     r9d, 12Ah; int
0x140018469  mov     edx, ebx; unsigned int
0x14001846b  lea     rcx, [rbp+pExceptionObject]; this
0x14001846f  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140018474  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001847b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14001847f  call    _CxxThrowException_0
0x140018485  lea     rcx, [rbp+arg_0]
0x140018489  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x14001848e  nop
0x14001848f  lea     rcx, [rbp+arg_18]
0x140018493  call    ??1?$AutoRef@VAbstractDomElement@@@wmi@@QEAA@XZ; wmi::AutoRef<AbstractDomElement>::~AutoRef<AbstractDomElement>(void)
0x140018498  add     rsp, 50h
0x14001849c  pop     r14
0x14001849e  pop     rdi
0x14001849f  pop     rsi
0x1400184a0  pop     rbx
0x1400184a1  pop     rbp
0x1400184a2  retn
```
