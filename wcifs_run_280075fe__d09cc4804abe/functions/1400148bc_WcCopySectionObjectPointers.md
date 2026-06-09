# WcCopySectionObjectPointers

- ea: `0x1400148bc`
- end: `0x1400149b8`
- name: `WcCopySectionObjectPointers`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140026de0`

## callees

- `0x1400024fc`
- `0x140004198`
- `0x1400148bc`

## import_xrefs

- `ntoskrnl!IoSetShadowFileInformation` at `0x140014936`
- `ntoskrnl!IoSetShadowFileInformation` at `0x140014936`
- `FLTMGR!FltGetStreamContext` at `0x1400148d7`
- `FLTMGR!FltGetStreamContext` at `0x1400148d7`
- `FLTMGR!FltReleaseContext` at `0x14001499e`
- `FLTMGR!FltReleaseContext` at `0x14001499e`

## string_xrefs

- `0x14001495f`: `onecore\base\fs\wci\wcifs\create.c`

## pseudocode

```c
__int64 __fastcall WcCopySectionObjectPointers(struct _FLT_INSTANCE *a1, struct _FILE_OBJECT *a2)
{
  NTSTATUS StreamContext; // ebx
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  int v8; // edx
  PFLT_CONTEXT Context; // [rsp+60h] [rbp+18h] BYREF

  Context = 0;
  StreamContext = FltGetStreamContext(a1, a2, &Context);
  if ( StreamContext >= 0 )
  {
    WcGetSource(Context);
    v6 = *(_QWORD *)WcGetSource(v4);
    a2->SectionObjectPointer = *(PSECTION_OBJECT_POINTERS *)(v5 + 40);
    _InterlockedIncrement((volatile signed __int32 *)(**(_QWORD **)(v7 + 32) + 24LL));
    if ( byte_14000E680 )
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(**((_QWORD **)Context + 4) + 32LL) + 4LL));
    StreamContext = IoSetShadowFileInformation(a2, v5, v6);
    if ( StreamContext < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 3;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        5,
        10,
        (__int64)WPP_852a4bc871f63f63d337338550f67970_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\create.c",
        121);
    }
  }
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)StreamContext;
}

```

## disassembly

```asm
0x1400148bc  mov     [rsp+arg_0], rbx
0x1400148c1  push    rdi
0x1400148c2  sub     rsp, 40h
0x1400148c6  lea     r8, [rsp+48h+Context]; Context
0x1400148cb  mov     [rsp+48h+Context], 0
0x1400148d4  mov     rdi, rdx
0x1400148d7  call    cs:__imp_FltGetStreamContext
0x1400148de  nop     dword ptr [rax+rax+00h]
0x1400148e3  mov     ebx, eax
0x1400148e5  test    eax, eax
0x1400148e7  js      loc_140014994
0x1400148ed  mov     rcx, [rsp+48h+Context]
0x1400148f2  call    WcGetSource
0x1400148f7  mov     rdx, [rax+10h]
0x1400148fb  call    WcGetSource
0x140014900  mov     r8, [rax]
0x140014903  mov     rax, [rdx+28h]
0x140014907  mov     [rdi+28h], rax
0x14001490b  mov     rax, [rcx+20h]
0x14001490f  mov     rcx, [rax]
0x140014912  lock inc dword ptr [rcx+18h]
0x140014916  cmp     cs:byte_14000E680, 0
0x14001491d  jz      short loc_140014933
0x14001491f  mov     rax, [rsp+48h+Context]
0x140014924  mov     rcx, [rax+20h]
0x140014928  mov     rax, [rcx]
0x14001492b  mov     rcx, [rax+20h]
0x14001492f  lock inc dword ptr [rcx+4]
0x140014933  mov     rcx, rdi
0x140014936  call    cs:__imp_IoSetShadowFileInformation
0x14001493d  nop     dword ptr [rax+rax+00h]
0x140014942  mov     ebx, eax
0x140014944  test    eax, eax
0x140014946  jns     short loc_140014994
0x140014948  lea     rax, WPP_RECORDER_INITIALIZED
0x14001494f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140014956  jz      short loc_140014994
0x140014958  mov     rcx, cs:WPP_GLOBAL_Control
0x14001495f  lea     rax, aOnecoreBaseFsW_4; "onecore\\base\\fs\\wci\\wcifs\\create.c"
0x140014966  mov     r9d, 0Ah
0x14001496c  mov     [rsp+48h+var_18], 79h ; 'y'
0x140014974  mov     [rsp+48h+var_20], rax
0x140014979  mov     dl, 3
0x14001497b  lea     rax, WPP_852a4bc871f63f63d337338550f67970_Traceguids
0x140014982  mov     rcx, [rcx+40h]
0x140014986  lea     r8d, [r9-5]
0x14001498a  mov     [rsp+48h+var_28], rax
0x14001498f  call    WPP_RECORDER_SF_sD
0x140014994  mov     rcx, [rsp+48h+Context]; Context
0x140014999  test    rcx, rcx
0x14001499c  jz      short loc_1400149AA
0x14001499e  call    cs:__imp_FltReleaseContext
0x1400149a5  nop     dword ptr [rax+rax+00h]
0x1400149aa  mov     eax, ebx
0x1400149ac  mov     rbx, [rsp+48h+arg_0]
0x1400149b1  add     rsp, 40h
0x1400149b5  pop     rdi
0x1400149b6  retn
```
