# EnableUWF(_UWF_CONFIG_OVERLAY_TYPE)

- ea: `0x18000f258`
- end: `0x18000f35c`
- name: `?EnableUWF@@YAJW4_UWF_CONFIG_OVERLAY_TYPE@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x180019a30`

## callees

- `0x18000e780`
- `0x18000ea14`
- `0x18000edc4`
- `0x18000ef58`
- `0x18000efbc`
- `0x18000f070`
- `0x18000f17c`
- `0x18000f258`
- `0x180010040`
- `0x180010a5c`
- `0x180010fc0`

## pseudocode

```c
__int64 __fastcall EnableUWF(int a1)
{
  int v2; // eax
  bool v3; // di
  int started; // ebx
  int v5; // eax
  bool v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  v2 = HaveCapturedUwfSettings(&v7);
  v3 = v7;
  if ( v2 < 0 )
    v3 = 0;
  started = SetBootStatusPolicy(L"IgnoreAllFailures");
  if ( started < 0 )
    goto LABEL_18;
  v5 = a1 ? MakePagingFilesFixedSize() : DisablePaging();
  started = v5;
  if ( v5 < 0 )
    goto LABEL_18;
  if ( !v3 )
  {
    started = DisableSystemRestore();
    if ( started < 0 )
      goto LABEL_18;
    started = DisableService(L"sysmain", 1u);
    if ( started < 0 )
      goto LABEL_18;
    started = DisableHiberboot();
    if ( started < 0 )
      goto LABEL_18;
    started = DisableService(L"cisvc", 1u);
    if ( started < 0 )
      goto LABEL_18;
    started = DisableService(L"defragsvc", 1u);
    if ( started < 0 )
      goto LABEL_18;
  }
  started = ConfigUWFDriversStartType(0);
  if ( started < 0
    || (started = ConfigLowerFiltersSetting(1), started < 0)
    || !v3 && (started = CaptureUwfSettings(0), started < 0) )
  {
LABEL_18:
    ConfigUWFDriversStartType(4u);
    ConfigLowerFiltersSetting(0);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000f258  mov     rax, rsp
0x18000f25b  mov     [rax+8], rbx
0x18000f25f  mov     [rax+18h], rsi
0x18000f263  push    rdi
0x18000f264  sub     rsp, 20h
0x18000f268  mov     esi, ecx
0x18000f26a  mov     byte ptr [rax+10h], 0
0x18000f26e  lea     rcx, [rax+10h]; bool *
0x18000f272  call    ?HaveCapturedUwfSettings@@YAJPEA_N@Z; HaveCapturedUwfSettings(bool *)
0x18000f277  movzx   edi, [rsp+28h+arg_8]
0x18000f27c  lea     rcx, aIgnoreallfailu; "IgnoreAllFailures"
0x18000f283  xor     edx, edx
0x18000f285  test    eax, eax
0x18000f287  cmovs   edi, edx
0x18000f28a  call    ?SetBootStatusPolicy@@YAJPEBG@Z; SetBootStatusPolicy(ushort const *)
0x18000f28f  mov     ebx, eax
0x18000f291  test    eax, eax
0x18000f293  js      loc_18000F339
0x18000f299  test    esi, esi
0x18000f29b  jnz     short loc_18000F2A4
0x18000f29d  call    ?DisablePaging@@YAJXZ; DisablePaging(void)
0x18000f2a2  jmp     short loc_18000F2A9
0x18000f2a4  call    ?MakePagingFilesFixedSize@@YAJXZ; MakePagingFilesFixedSize(void)
0x18000f2a9  mov     ebx, eax
0x18000f2ab  test    eax, eax
0x18000f2ad  js      loc_18000F339
0x18000f2b3  test    dil, dil
0x18000f2b6  jnz     short loc_18000F30A
0x18000f2b8  call    ?DisableSystemRestore@@YAJXZ; DisableSystemRestore(void)
0x18000f2bd  mov     ebx, eax
0x18000f2bf  test    eax, eax
0x18000f2c1  js      short loc_18000F339
0x18000f2c3  mov     dl, 1; bool
0x18000f2c5  lea     rcx, aSysmain; "sysmain"
0x18000f2cc  call    ?DisableService@@YAJPEBG_N@Z; DisableService(ushort const *,bool)
0x18000f2d1  mov     ebx, eax
0x18000f2d3  test    eax, eax
0x18000f2d5  js      short loc_18000F339
0x18000f2d7  call    ?DisableHiberboot@@YAJXZ; DisableHiberboot(void)
0x18000f2dc  mov     ebx, eax
0x18000f2de  test    eax, eax
0x18000f2e0  js      short loc_18000F339
0x18000f2e2  mov     dl, 1; bool
0x18000f2e4  lea     rcx, aCisvc; "cisvc"
0x18000f2eb  call    ?DisableService@@YAJPEBG_N@Z; DisableService(ushort const *,bool)
0x18000f2f0  mov     ebx, eax
0x18000f2f2  test    eax, eax
0x18000f2f4  js      short loc_18000F339
0x18000f2f6  mov     dl, 1; bool
0x18000f2f8  lea     rcx, ServiceName; "defragsvc"
0x18000f2ff  call    ?DisableService@@YAJPEBG_N@Z; DisableService(ushort const *,bool)
0x18000f304  mov     ebx, eax
0x18000f306  test    eax, eax
0x18000f308  js      short loc_18000F339
0x18000f30a  xor     ecx, ecx; dwStartType
0x18000f30c  call    ?ConfigUWFDriversStartType@@YAJK@Z; ConfigUWFDriversStartType(ulong)
0x18000f311  mov     ebx, eax
0x18000f313  test    eax, eax
0x18000f315  js      short loc_18000F339
0x18000f317  mov     ecx, 1; int
0x18000f31c  call    ?ConfigLowerFiltersSetting@@YAJH@Z; ConfigLowerFiltersSetting(int)
0x18000f321  mov     ebx, eax
0x18000f323  test    eax, eax
0x18000f325  js      short loc_18000F339
0x18000f327  test    dil, dil
0x18000f32a  jnz     short loc_18000F34A
0x18000f32c  xor     ecx, ecx
0x18000f32e  call    ?CaptureUwfSettings@@YAJW4E_UNATTEND_REASON@@@Z; CaptureUwfSettings(E_UNATTEND_REASON)
0x18000f333  mov     ebx, eax
0x18000f335  test    eax, eax
0x18000f337  jns     short loc_18000F34A
0x18000f339  mov     ecx, 4; dwStartType
0x18000f33e  call    ?ConfigUWFDriversStartType@@YAJK@Z; ConfigUWFDriversStartType(ulong)
0x18000f343  xor     ecx, ecx; int
0x18000f345  call    ?ConfigLowerFiltersSetting@@YAJH@Z; ConfigLowerFiltersSetting(int)
0x18000f34a  mov     rsi, [rsp+28h+arg_10]
0x18000f34f  mov     eax, ebx
0x18000f351  mov     rbx, [rsp+28h+arg_0]
0x18000f356  add     rsp, 20h
0x18000f35a  pop     rdi
0x18000f35b  retn
```
