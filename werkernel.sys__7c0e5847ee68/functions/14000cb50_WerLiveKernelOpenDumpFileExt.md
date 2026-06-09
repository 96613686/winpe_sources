# WerLiveKernelOpenDumpFileExt

- ea: `0x14000cb50`
- end: `0x14000cc40`
- name: `WerLiveKernelOpenDumpFileExt`
- size: `240`
- prototype: `__int64 __fastcall(_DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000cb50`
- `0x14000dc94`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000cb95`
- `ntoskrnl!DbgPrintEx` at `0x14000cbd5`
- `ntoskrnl!DbgPrintEx` at `0x14000cbfc`
- `ntoskrnl!DbgPrintEx` at `0x14000cc1e`
- `ntoskrnl!DbgPrintEx` at `0x14000cb95`
- `ntoskrnl!DbgPrintEx` at `0x14000cbd5`
- `ntoskrnl!DbgPrintEx` at `0x14000cbfc`
- `ntoskrnl!DbgPrintEx` at `0x14000cc1e`

## string_xrefs

- `0x14000cc0f`: `WERKERNELHOST:  WerLiveKernelOpenDumpFileExt: Invalid parameter\n`
- `0x14000cba1`: `WERKERNELHOST: WerLiveKernelOpenDumpFileExt: invalid context.\n`
- `0x14000cbcb`: `WERKERNELHOST: WepCreateDumpFile failed, status 0x%x\n`
- `0x14000cbe8`: `WERKERNELHOST: WerLiveKernelOpenDumpFileExt: returning dump handle %p, report reportHandle %p\n`

## pseudocode

```c
__int64 __fastcall WerLiveKernelOpenDumpFileExt(_DWORD *a1, _QWORD *a2)
{
  int v4; // eax
  unsigned int v5; // esi
  void *v6; // rbx
  const void *v8; // [rsp+20h] [rbp-18h]
  void *v9; // [rsp+40h] [rbp+8h] BYREF

  if ( !a1 || !a2 )
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST:  WerLiveKernelOpenDumpFileExt: Invalid parameter\n");
    return 3221225485LL;
  }
  *a2 = 0;
  if ( *a1 != 1667984471 )
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: WER context signature validation failed! \n");
    DbgPrintEx(5u, 1u, "WERKERNELHOST: WerLiveKernelOpenDumpFileExt: invalid context.\n");
    return 3221225485LL;
  }
  v9 = 0;
  v4 = WerpCreateDumpFile((__int64)a1, &v9);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v8 = a1;
    v6 = v9;
    DbgPrintEx(
      5u,
      3u,
      "WERKERNELHOST: WerLiveKernelOpenDumpFileExt: returning dump handle %p, report reportHandle %p\n",
      v9,
      v8);
    *a2 = v6;
  }
  else
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: WepCreateDumpFile failed, status 0x%x\n", v4);
  }
  return v5;
}

```

## disassembly

```asm
0x14000cb50  mov     [rsp+arg_8], rbx
0x14000cb55  mov     [rsp+arg_10], rsi
0x14000cb5a  push    rdi
0x14000cb5b  sub     rsp, 30h
0x14000cb5f  mov     rdi, rdx
0x14000cb62  mov     rbx, rcx
0x14000cb65  test    rcx, rcx
0x14000cb68  jz      loc_14000CC0F
0x14000cb6e  test    rdx, rdx
0x14000cb71  jz      loc_14000CC0F
0x14000cb77  mov     qword ptr [rdx], 0
0x14000cb7e  cmp     dword ptr [rcx], 636B6C57h
0x14000cb84  jz      short loc_14000CBAA
0x14000cb86  mov     edx, 1; Level
0x14000cb8b  lea     r8, aWerkernelhostW_8; "WERKERNELHOST: WER context signature va"...
0x14000cb92  lea     ecx, [rdx+4]; ComponentId
0x14000cb95  call    cs:__imp_DbgPrintEx
0x14000cb9c  nop     dword ptr [rax+rax+00h]
0x14000cba1  lea     r8, aWerkernelhostW_60; "WERKERNELHOST: WerLiveKernelOpenDumpFil"...
0x14000cba8  jmp     short loc_14000CC16
0x14000cbaa  lea     rdx, [rsp+38h+arg_0]
0x14000cbaf  mov     [rsp+38h+arg_0], 0
0x14000cbb8  call    WerpCreateDumpFile
0x14000cbbd  mov     esi, eax
0x14000cbbf  mov     ecx, 5; ComponentId
0x14000cbc4  test    eax, eax
0x14000cbc6  jns     short loc_14000CBE3
0x14000cbc8  mov     r9d, eax
0x14000cbcb  lea     r8, aWerkernelhostW_57; "WERKERNELHOST: WepCreateDumpFile failed"...
0x14000cbd2  lea     edx, [rcx-4]; Level
0x14000cbd5  call    cs:__imp_DbgPrintEx
0x14000cbdc  nop     dword ptr [rax+rax+00h]
0x14000cbe1  jmp     short loc_14000CC0B
0x14000cbe3  mov     [rsp+38h+var_18], rbx
0x14000cbe8  lea     r8, aWerkernelhostW_11; "WERKERNELHOST: WerLiveKernelOpenDumpFil"...
0x14000cbef  mov     rbx, [rsp+38h+arg_0]
0x14000cbf4  mov     edx, 3; Level
0x14000cbf9  mov     r9, rbx
0x14000cbfc  call    cs:__imp_DbgPrintEx
0x14000cc03  nop     dword ptr [rax+rax+00h]
0x14000cc08  mov     [rdi], rbx
0x14000cc0b  mov     eax, esi
0x14000cc0d  jmp     short loc_14000CC2F
0x14000cc0f  lea     r8, aWerkernelhostW_18; "WERKERNELHOST:  WerLiveKernelOpenDumpFi"...
0x14000cc16  mov     edx, 1; Level
0x14000cc1b  lea     ecx, [rdx+4]; ComponentId
0x14000cc1e  call    cs:__imp_DbgPrintEx
0x14000cc25  nop     dword ptr [rax+rax+00h]
0x14000cc2a  mov     eax, 0C000000Dh
0x14000cc2f  mov     rbx, [rsp+38h+arg_8]
0x14000cc34  mov     rsi, [rsp+38h+arg_10]
0x14000cc39  add     rsp, 30h
0x14000cc3d  pop     rdi
0x14000cc3e  retn
```
