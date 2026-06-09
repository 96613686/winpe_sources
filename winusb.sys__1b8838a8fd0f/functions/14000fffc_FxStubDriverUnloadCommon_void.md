# FxStubDriverUnloadCommon(void)

- ea: `0x14000fffc`
- end: `0x1400100f3`
- name: `?FxStubDriverUnloadCommon@@YAXXZ`
- size: `247`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140010134`
- `0x1400102b0`

## callees

- `0x14000fffc`
- `0x140010700`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400100ba`
- `ntoskrnl!DbgPrintEx` at `0x1400100ba`
- `WDFLDR!WdfVersionUnbindClass` at `0x14001009b`
- `WDFLDR!WdfVersionUnbindClass` at `0x140010079`
- `WDFLDR!WdfVersionUnbindClass` at `0x14001009b`
- `WDFLDR!WdfVersionUnbind` at `0x1400100db`
- `WDFLDR!WdfVersionUnbind` at `0x1400100db`

## pseudocode

```c
void FxStubDriverUnloadCommon(void)
{
  void **v0; // rcx
  void **v1; // rdi
  void **v2; // rbx
  void (__fastcall *v3)(_QWORD, _QWORD, _QWORD, _QWORD); // rax

  if ( off_1400151D8 != (struct _MARKER_TYPE *)&__KMDF_CLASS_BIND_START )
  {
    v0 = &__KMDF_CLASS_BIND_END;
    v1 = (void **)((char *)off_1400151D8 + 80);
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
        v3(WdfVersionUnbindClass, &WdfBindInfo, WdfDriverGlobals, v2);
      else
        WdfVersionUnbindClass(&WdfBindInfo, WdfDriverGlobals, v2);
      v0 = (void **)((char *)v2 + *(unsigned int *)v2);
    }
  }
  WdfVersionUnbind(&DestinationString, &WdfBindInfo, WdfDriverGlobals);
}

```

## disassembly

```asm
0x14000fffc  mov     [rsp+arg_0], rbx
0x140010001  push    rdi
0x140010002  sub     rsp, 30h
0x140010006  mov     rdi, cs:off_1400151D8
0x14001000d  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140010014  cmp     rdi, rax
0x140010017  jz      loc_1400100C6
0x14001001d  lea     rcx, ?__KMDF_CLASS_BIND_END@@3PEAXEA; void * __KMDF_CLASS_BIND_END
0x140010024  add     rdi, 50h ; 'P'
0x140010028  jmp     short loc_140010034
0x14001002a  cmp     qword ptr [rcx], 0
0x14001002e  jnz     short loc_14001003D
0x140010030  add     rcx, 8
0x140010034  lea     rax, [rcx+8]
0x140010038  cmp     rax, rdi
0x14001003b  jbe     short loc_14001002A
0x14001003d  cmp     rcx, rdi
0x140010040  jb      short loc_140010047
0x140010042  mov     rbx, rdi
0x140010045  jmp     short loc_140010058
0x140010047  lea     rax, [rcx+50h]
0x14001004b  cmp     rax, rdi
0x14001004e  ja      short loc_1400100AE
0x140010050  cmp     dword ptr [rcx], 50h ; 'P'
0x140010053  jnz     short loc_1400100AE
0x140010055  mov     rbx, rcx
0x140010058  test    rbx, rbx
0x14001005b  jz      short loc_1400100AE
0x14001005d  cmp     rbx, rdi
0x140010060  jnb     short loc_1400100C6
0x140010062  mov     rax, [rbx+40h]
0x140010066  test    rax, rax
0x140010069  jz      short loc_14001008A
0x14001006b  mov     r8, cs:WdfDriverGlobals
0x140010072  lea     rdx, WdfBindInfo
0x140010079  mov     rcx, cs:__imp_WdfVersionUnbindClass
0x140010080  mov     r9, rbx
0x140010083  call    _guard_dispatch_icall
0x140010088  jmp     short loc_1400100A7
0x14001008a  mov     rdx, cs:WdfDriverGlobals
0x140010091  lea     rcx, WdfBindInfo
0x140010098  mov     r8, rbx
0x14001009b  call    cs:__imp_WdfVersionUnbindClass
0x1400100a2  nop     dword ptr [rax+rax+00h]
0x1400100a7  mov     ecx, [rbx]
0x1400100a9  add     rcx, rbx
0x1400100ac  jmp     short loc_140010034
0x1400100ae  xor     edx, edx; Level
0x1400100b0  lea     r8, Format; "FxGetNextClassBindInfo failed\n"
0x1400100b7  lea     ecx, [rdx+4Dh]; ComponentId
0x1400100ba  call    cs:__imp_DbgPrintEx
0x1400100c1  nop     dword ptr [rax+rax+00h]
0x1400100c6  mov     r8, cs:WdfDriverGlobals
0x1400100cd  lea     rdx, WdfBindInfo
0x1400100d4  lea     rcx, DestinationString
0x1400100db  call    cs:__imp_WdfVersionUnbind
0x1400100e2  nop     dword ptr [rax+rax+00h]
0x1400100e7  mov     rbx, [rsp+38h+arg_0]
0x1400100ec  add     rsp, 30h
0x1400100f0  pop     rdi
0x1400100f1  retn
```
