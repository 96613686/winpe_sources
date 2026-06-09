# LogSurpriseRemovalCount(uchar)

- ea: `0x1800078e0`
- end: `0x1800079ba`
- name: `?LogSurpriseRemovalCount@@YAXE@Z`
- size: `218`
- prototype: `void __fastcall(char)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180005da0`

## callees

- `0x180001294`
- `0x180001990`
- `0x1800078e0`
- `0x18000bc7c`
- `0x18000bd24`
- `0x18000c088`
- `0x18000c114`
- `0x18000c16c`

## string_xrefs

- `0x180007939`: `BootPathSurpriseRemovalCount`
- `0x18000794e`: `BootPathSurpriseRemovalCount`

## pseudocode

```c
void __fastcall LogSurpriseRemovalCount(char a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // r8
  __int64 v6; // r9
  HKEY phkResult[5]; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+68h] [rbp+10h] BYREF
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v8 = 0;
  if ( CRegistryKey::KeyExists(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Usb\\Ceip") )
  {
    CRegistryKey::CRegistryKey(phkResult, HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Usb\\Ceip");
    v8 = 0;
    CRegistryKey::QueryFixedLengthValue(
      (CRegistryKey *)phkResult,
      L"BootPathSurpriseRemovalCount",
      4u,
      (unsigned __int8 *)&v8);
    if ( !a1 )
      CRegistryKey::SetUlongValue(phkResult, L"BootPathSurpriseRemovalCount");
    CRegistryKey::~CRegistryKey(phkResult);
  }
  else
  {
    v8 = 0;
  }
  if ( (unsigned int)dword_18001C000 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_18001C000, v2, v3, v4) )
    {
      v9 = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18001C000,
        (__int64)qword_180017DE0,
        v5,
        v6,
        (__int64)&v9);
    }
  }
}

```

## disassembly

```asm
0x1800078e0  push    rbx
0x1800078e2  sub     rsp, 50h
0x1800078e6  mov     bl, cl
0x1800078e8  mov     [rsp+58h+arg_8], 0
0x1800078f0  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Usb"...
0x1800078f7  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800078fe  call    ?KeyExists@CRegistryKey@@SAEPEAUHKEY__@@PEBG@Z; CRegistryKey::KeyExists(HKEY__ *,ushort const *)
0x180007903  test    al, al
0x180007905  jz      short loc_18000796C
0x180007907  mov     r9d, 3; unsigned int
0x18000790d  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Usb"...
0x180007914  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18000791b  lea     rcx, [rsp+58h+phkResult]; phkResult
0x180007920  call    ??0CRegistryKey@@QEAA@PEAUHKEY__@@PEBGK@Z; CRegistryKey::CRegistryKey(HKEY__ *,ushort const *,ulong)
0x180007925  nop
0x180007926  mov     [rsp+58h+arg_8], 0
0x18000792e  lea     r9, [rsp+58h+arg_8]; unsigned __int8 *
0x180007933  mov     r8d, 4; unsigned int
0x180007939  lea     rdx, aBootpathsurpri; "BootPathSurpriseRemovalCount"
0x180007940  lea     rcx, [rsp+58h+phkResult]; this
0x180007945  call    ?QueryFixedLengthValue@CRegistryKey@@QEAAEPEBGKPEAE@Z; CRegistryKey::QueryFixedLengthValue(ushort const *,ulong,uchar *)
0x18000794a  test    bl, bl
0x18000794c  jnz     short loc_180007960
0x18000794e  lea     rdx, aBootpathsurpri; "BootPathSurpriseRemovalCount"
0x180007955  lea     rcx, [rsp+58h+phkResult]; this
0x18000795a  call    ?SetUlongValue@CRegistryKey@@QEAAXPEBGK@Z; CRegistryKey::SetUlongValue(ushort const *,ulong)
0x18000795f  nop
0x180007960  lea     rcx, [rsp+58h+phkResult]; this
0x180007965  call    ??1CRegistryKey@@QEAA@XZ; CRegistryKey::~CRegistryKey(void)
0x18000796a  jmp     short loc_180007974
0x18000796c  mov     [rsp+58h+arg_8], 0
0x180007974  mov     eax, cs:dword_18001C000
0x18000797a  cmp     eax, 5
0x18000797d  jbe     short loc_1800079B4
0x18000797f  lea     rcx, dword_18001C000
0x180007986  call    _tlgKeywordOn
0x18000798b  test    al, al
0x18000798d  jz      short loc_1800079B4
0x18000798f  mov     eax, [rsp+58h+arg_8]
0x180007993  mov     [rsp+58h+arg_10], eax
0x180007997  lea     rax, [rsp+58h+arg_10]
0x18000799c  mov     [rsp+58h+var_38], rax
0x1800079a1  lea     rdx, qword_180017DE0
0x1800079a8  lea     rcx, dword_18001C000
0x1800079af  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800079b4  add     rsp, 50h
0x1800079b8  pop     rbx
0x1800079b9  retn
```
