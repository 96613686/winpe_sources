# FxStubDriverUnloadCommon(void)

- ea: `0x14000a330`
- end: `0x14000a427`
- name: `?FxStubDriverUnloadCommon@@YAXXZ`
- size: `247`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a464`
- `0x14000a5e0`

## callees

- `0x14000a330`
- `0x14000aa30`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000a3ee`
- `ntoskrnl!DbgPrintEx` at `0x14000a3ee`
- `WDFLDR!WdfVersionUnbindClass` at `0x14000a3cf`
- `WDFLDR!WdfVersionUnbindClass` at `0x14000a3ad`
- `WDFLDR!WdfVersionUnbindClass` at `0x14000a3cf`
- `WDFLDR!WdfVersionUnbind` at `0x14000a40f`
- `WDFLDR!WdfVersionUnbind` at `0x14000a40f`

## pseudocode

```c
void FxStubDriverUnloadCommon(void)
{
  void **v0; // rcx
  void **v1; // rdi
  void **v2; // rbx
  void (__fastcall *v3)(_QWORD, _QWORD, _QWORD, _QWORD); // rax

  if ( off_14000F328 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
  {
    v0 = &__KMDF_CLASS_BIND_END;
    v1 = (void **)((char *)off_14000F328 + 80);
    while ( 1 )
    {
      while ( v0 + 1 <= v1 && !*v0 )
        ++v0;
      if ( v0 < v1 )
      {
        if ( v0 + 10 > v1 || *(_DWORD *)v0 != 80 )
        {
LABEL_17:
          DbgPrintEx(0x4Du, 0, "FxGetNextClassBindInfo failed\n");
          break;
        }
        v2 = v0;
      }
      else
      {
        v2 = v1;
      }
      if ( !v2 )
        goto LABEL_17;
      if ( v2 >= v1 )
        break;
      v3 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v2[8];
      if ( v3 )
        v3(WdfVersionUnbindClass, &WdfBindInfo, WPP_MAIN_CB.Queue.ListEntry.Blink, v2);
      else
        WdfVersionUnbindClass(&WdfBindInfo, WPP_MAIN_CB.Queue.ListEntry.Blink, v2);
      v0 = (void **)((char *)v2 + *(unsigned int *)v2);
    }
  }
  WdfVersionUnbind(&WPP_MAIN_CB.DeviceExtension, &WdfBindInfo, WPP_MAIN_CB.Queue.ListEntry.Blink);
}

```

## disassembly

```asm
0x14000a330  mov     [rsp+arg_0], rbx
0x14000a335  push    rdi
0x14000a336  sub     rsp, 30h
0x14000a33a  mov     rdi, cs:off_14000F328
0x14000a341  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x14000a348  cmp     rdi, rax
0x14000a34b  jz      loc_14000A3FA
0x14000a351  lea     rcx, ?__KMDF_CLASS_BIND_END@@3PEAXEA; void * __KMDF_CLASS_BIND_END
0x14000a358  add     rdi, 50h ; 'P'
0x14000a35c  jmp     short loc_14000A368
0x14000a35e  cmp     qword ptr [rcx], 0
0x14000a362  jnz     short loc_14000A371
0x14000a364  add     rcx, 8
0x14000a368  lea     rax, [rcx+8]
0x14000a36c  cmp     rax, rdi
0x14000a36f  jbe     short loc_14000A35E
0x14000a371  cmp     rcx, rdi
0x14000a374  jb      short loc_14000A37B
0x14000a376  mov     rbx, rdi
0x14000a379  jmp     short loc_14000A38C
0x14000a37b  lea     rax, [rcx+50h]
0x14000a37f  cmp     rax, rdi
0x14000a382  ja      short loc_14000A3E2
0x14000a384  cmp     dword ptr [rcx], 50h ; 'P'
0x14000a387  jnz     short loc_14000A3E2
0x14000a389  mov     rbx, rcx
0x14000a38c  test    rbx, rbx
0x14000a38f  jz      short loc_14000A3E2
0x14000a391  cmp     rbx, rdi
0x14000a394  jnb     short loc_14000A3FA
0x14000a396  mov     rax, [rbx+40h]
0x14000a39a  test    rax, rax
0x14000a39d  jz      short loc_14000A3BE
0x14000a39f  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000a3a6  lea     rdx, WdfBindInfo
0x14000a3ad  mov     rcx, cs:__imp_WdfVersionUnbindClass
0x14000a3b4  mov     r9, rbx
0x14000a3b7  call    _guard_dispatch_icall
0x14000a3bc  jmp     short loc_14000A3DB
0x14000a3be  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000a3c5  lea     rcx, WdfBindInfo
0x14000a3cc  mov     r8, rbx
0x14000a3cf  call    cs:__imp_WdfVersionUnbindClass
0x14000a3d6  nop     dword ptr [rax+rax+00h]
0x14000a3db  mov     ecx, [rbx]
0x14000a3dd  add     rcx, rbx
0x14000a3e0  jmp     short loc_14000A368
0x14000a3e2  xor     edx, edx; Level
0x14000a3e4  lea     r8, Format; "FxGetNextClassBindInfo failed\n"
0x14000a3eb  lea     ecx, [rdx+4Dh]; ComponentId
0x14000a3ee  call    cs:__imp_DbgPrintEx
0x14000a3f5  nop     dword ptr [rax+rax+00h]
0x14000a3fa  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+8
0x14000a401  lea     rdx, WdfBindInfo
0x14000a408  lea     rcx, WPP_MAIN_CB.DeviceExtension
0x14000a40f  call    cs:__imp_WdfVersionUnbind
0x14000a416  nop     dword ptr [rax+rax+00h]
0x14000a41b  mov     rbx, [rsp+38h+arg_0]
0x14000a420  add     rsp, 30h
0x14000a424  pop     rdi
0x14000a425  retn
```
