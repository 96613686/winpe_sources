# pAddImageEnumFlags(_IMG_SERVER_CONTEXT *,CImgSrvPacket *)

- ea: `0x180007b18`
- end: `0x180007c20`
- name: `?pAddImageEnumFlags@@YAKPEAU_IMG_SERVER_CONTEXT@@PEAVCImgSrvPacket@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(struct _IMG_SERVER_CONTEXT *, struct CImgSrvPacket *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003838`

## callees

- `0x180002918`
- `0x180006a58`
- `0x180007b18`
- `0x180007fd8`
- `0x1800119d4`

## import_xrefs

- `WdsCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180007b73`
- `WdsCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180007bb2`
- `WdsCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180007b73`
- `WdsCommonLib!?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z` at `0x180007bb2`

## string_xrefs

- `0x180007b30`: `System\CurrentControlSet\Services\WdsServer\Providers\WdsImgSrv`

## pseudocode

```c
__int64 __fastcall pAddImageEnumFlags(
        struct _IMG_SERVER_CONTEXT *a1,
        struct CImgSrvPacket *a2,
        __int64 a3,
        unsigned int a4)
{
  int v4; // esi
  unsigned int ValueDwordWithDefault; // ebx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v15; // [rsp+40h] [rbp+8h] BYREF
  int v16; // [rsp+44h] [rbp+Ch]
  HKEY v17; // [rsp+50h] [rbp+18h] BYREF

  v16 = HIDWORD(a1);
  v15 = 0;
  v17 = 0;
  v4 = (int)a2;
  ValueDwordWithDefault = CRegKey::Open(
                            &v17,
                            (HKEY)a2,
                            L"System\\CurrentControlSet\\Services\\WdsServer\\Providers\\WdsImgSrv",
                            a4);
  if ( !(unsigned int)ElValidateWin32(ValueDwordWithDefault, v6, v7, 260) )
  {
    ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault((CRegKey *)&v17, L"FilterImageVersion", 0, &v15);
    if ( !(unsigned int)ElValidateWin32(ValueDwordWithDefault, v8, v9, 268) )
    {
      ValueDwordWithDefault = CRegKey::GetValueDwordWithDefault((CRegKey *)&v17, L"FilterFirmware", 0, &v15);
      if ( !(unsigned int)ElValidateWin32(ValueDwordWithDefault, v10, v11, 281) )
      {
        ValueDwordWithDefault = CControlPacket::AddVariable<unsigned long>(v4, (unsigned int)L"OPTIONS", 0, -1);
        ElValidateWin32(ValueDwordWithDefault, v12, v13, 293);
      }
    }
  }
  CRegKey::Close((CRegKey *)&v17);
  return ValueDwordWithDefault;
}

```

## disassembly

```asm
0x180007b18  mov     rax, rsp
0x180007b1b  mov     [rax+10h], rbx
0x180007b1f  mov     [rax+20h], rsi
0x180007b23  mov     [rax+8], rcx
0x180007b27  push    rdi
0x180007b28  sub     rsp, 30h
0x180007b2c  and     dword ptr [rax+8], 0
0x180007b30  lea     r8, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Wd"...
0x180007b37  and     qword ptr [rax+18h], 0
0x180007b3c  lea     rcx, [rax+18h]; phkResult
0x180007b40  mov     rsi, rdx
0x180007b43  call    ?Open@CRegKey@@QEAAKPEAUHKEY__@@PEBGK@Z; CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180007b48  mov     r9d, 104h
0x180007b4e  mov     ecx, eax
0x180007b50  mov     ebx, eax
0x180007b52  call    ElValidateWin32
0x180007b57  test    eax, eax
0x180007b59  jnz     loc_180007C03
0x180007b5f  lea     r9, [rsp+38h+arg_0]
0x180007b64  xor     r8d, r8d
0x180007b67  lea     rdx, aFilterimagever; "FilterImageVersion"
0x180007b6e  lea     rcx, [rsp+38h+arg_10]
0x180007b73  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180007b7a  nop     dword ptr [rax+rax+00h]
0x180007b7f  mov     ecx, eax
0x180007b81  mov     r9d, 10Ch
0x180007b87  mov     ebx, eax
0x180007b89  call    ElValidateWin32
0x180007b8e  test    eax, eax
0x180007b90  jnz     short loc_180007C03
0x180007b92  xor     edi, edi
0x180007b94  lea     r9, [rsp+38h+arg_0]
0x180007b99  cmp     [rsp+38h+arg_0], edi
0x180007b9d  lea     rdx, aFilterfirmware; "FilterFirmware"
0x180007ba4  lea     rcx, [rsp+38h+arg_10]
0x180007ba9  lea     eax, [rdi+1]
0x180007bac  cmovnz  edi, eax
0x180007baf  xor     r8d, r8d
0x180007bb2  call    cs:__imp_?GetValueDwordWithDefault@CRegKey@@QEAAKPEBGKPEAK@Z; CRegKey::GetValueDwordWithDefault(ushort const *,ulong,ulong *)
0x180007bb9  nop     dword ptr [rax+rax+00h]
0x180007bbe  mov     ecx, eax
0x180007bc0  mov     r9d, 119h
0x180007bc6  mov     ebx, eax
0x180007bc8  call    ElValidateWin32
0x180007bcd  test    eax, eax
0x180007bcf  jnz     short loc_180007C03
0x180007bd1  cmp     [rsp+38h+arg_0], eax
0x180007bd5  jz      short loc_180007BDA
0x180007bd7  or      edi, 2
0x180007bda  or      r9d, 0FFFFFFFFh
0x180007bde  mov     [rsp+38h+var_10], edi
0x180007be2  xor     r8d, r8d
0x180007be5  lea     rdx, aOptions; "OPTIONS"
0x180007bec  mov     rcx, rsi
0x180007bef  call    ??$AddVariable@K@CControlPacket@@QEAAKPEBG0KKK@Z; CControlPacket::AddVariable<ulong>(ushort const *,ushort const *,ulong,ulong,ulong)
0x180007bf4  mov     r9d, 125h
0x180007bfa  mov     ecx, eax
0x180007bfc  mov     ebx, eax
0x180007bfe  call    ElValidateWin32
0x180007c03  lea     rcx, [rsp+38h+arg_10]; this
0x180007c08  call    ?Close@CRegKey@@QEAAXXZ; CRegKey::Close(void)
0x180007c0d  mov     rsi, [rsp+38h+arg_18]
0x180007c12  mov     eax, ebx
0x180007c14  mov     rbx, [rsp+38h+arg_8]
0x180007c19  add     rsp, 30h
0x180007c1d  pop     rdi
0x180007c1e  retn
```
