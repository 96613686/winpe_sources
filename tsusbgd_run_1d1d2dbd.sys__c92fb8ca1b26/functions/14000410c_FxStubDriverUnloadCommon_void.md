# FxStubDriverUnloadCommon(void)

- ea: `0x14000410c`
- end: `0x140004203`
- name: `?FxStubDriverUnloadCommon@@YAXXZ`
- size: `247`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004244`
- `0x1400043c0`

## callees

- `0x14000410c`
- `0x140006370`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400041ca`
- `ntoskrnl!DbgPrintEx` at `0x1400041ca`
- `WDFLDR!WdfVersionUnbindClass` at `0x1400041ab`
- `WDFLDR!WdfVersionUnbindClass` at `0x140004189`
- `WDFLDR!WdfVersionUnbindClass` at `0x1400041ab`
- `WDFLDR!WdfVersionUnbind` at `0x1400041eb`
- `WDFLDR!WdfVersionUnbind` at `0x1400041eb`

## pseudocode

```c
void FxStubDriverUnloadCommon(void)
{
  unsigned int *v0; // rcx
  unsigned int *v1; // rdi
  unsigned int *v2; // rbx
  void (__fastcall *v3)(__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), void *, struct _LIST_ENTRY *, unsigned int *); // rax

  if ( off_140009158 != &__KMDF_CLASS_BIND_START )
  {
    v0 = (unsigned int *)&__KMDF_CLASS_BIND_END;
    v1 = (unsigned int *)((char *)off_140009158 + 80);
    while ( 1 )
    {
      while ( v0 + 2 <= v1 && !*(_QWORD *)v0 )
        v0 += 2;
      if ( v0 < v1 )
      {
        if ( v0 + 20 > v1 || *v0 != 80 )
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
      v3 = (void (__fastcall *)(__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), void *, struct _LIST_ENTRY *, unsigned int *))*((_QWORD *)v2 + 8);
      if ( v3 )
        v3(WdfVersionUnbindClass, &WdfBindInfo, WPP_MAIN_CB.Queue.ListEntry.Blink, v2);
      else
        WdfVersionUnbindClass(&WdfBindInfo, WPP_MAIN_CB.Queue.ListEntry.Blink, v2);
      v0 = (unsigned int *)((char *)v2 + *v2);
    }
  }
  WdfVersionUnbind(&WPP_MAIN_CB.DeviceExtension, &WdfBindInfo, WPP_MAIN_CB.Queue.ListEntry.Blink);
}

```

## disassembly

```asm
0x14000410c  mov     [rsp+arg_0], rbx
0x140004111  push    rdi
0x140004112  sub     rsp, 30h
0x140004116  mov     rdi, cs:off_140009158
0x14000411d  lea     rax, ?__KMDF_CLASS_BIND_START@@3U_MARKER_TYPE@@A; _MARKER_TYPE __KMDF_CLASS_BIND_START
0x140004124  cmp     rdi, rax
0x140004127  jz      loc_1400041D6
0x14000412d  lea     rcx, ?__KMDF_CLASS_BIND_END@@3PEAXEA; void * __KMDF_CLASS_BIND_END
0x140004134  add     rdi, 50h ; 'P'
0x140004138  jmp     short loc_140004144
0x14000413a  cmp     qword ptr [rcx], 0
0x14000413e  jnz     short loc_14000414D
0x140004140  add     rcx, 8
0x140004144  lea     rax, [rcx+8]
0x140004148  cmp     rax, rdi
0x14000414b  jbe     short loc_14000413A
0x14000414d  cmp     rcx, rdi
0x140004150  jb      short loc_140004157
0x140004152  mov     rbx, rdi
0x140004155  jmp     short loc_140004168
0x140004157  lea     rax, [rcx+50h]
0x14000415b  cmp     rax, rdi
0x14000415e  ja      short loc_1400041BE
0x140004160  cmp     dword ptr [rcx], 50h ; 'P'
0x140004163  jnz     short loc_1400041BE
0x140004165  mov     rbx, rcx
0x140004168  test    rbx, rbx
0x14000416b  jz      short loc_1400041BE
0x14000416d  cmp     rbx, rdi
0x140004170  jnb     short loc_1400041D6
0x140004172  mov     rax, [rbx+40h]
0x140004176  test    rax, rax
0x140004179  jz      short loc_14000419A
0x14000417b  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140004182  lea     rdx, WdfBindInfo
0x140004189  mov     rcx, cs:__imp_WdfVersionUnbindClass
0x140004190  mov     r9, rbx
0x140004193  call    _guard_dispatch_icall
0x140004198  jmp     short loc_1400041B7
0x14000419a  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400041a1  lea     rcx, WdfBindInfo
0x1400041a8  mov     r8, rbx
0x1400041ab  call    cs:__imp_WdfVersionUnbindClass
0x1400041b2  nop     dword ptr [rax+rax+00h]
0x1400041b7  mov     ecx, [rbx]
0x1400041b9  add     rcx, rbx
0x1400041bc  jmp     short loc_140004144
0x1400041be  xor     edx, edx; Level
0x1400041c0  lea     r8, Format; "FxGetNextClassBindInfo failed\n"
0x1400041c7  lea     ecx, [rdx+4Dh]; ComponentId
0x1400041ca  call    cs:__imp_DbgPrintEx
0x1400041d1  nop     dword ptr [rax+rax+00h]
0x1400041d6  mov     r8, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400041dd  lea     rdx, WdfBindInfo
0x1400041e4  lea     rcx, WPP_MAIN_CB.DeviceExtension
0x1400041eb  call    cs:__imp_WdfVersionUnbind
0x1400041f2  nop     dword ptr [rax+rax+00h]
0x1400041f7  mov     rbx, [rsp+38h+arg_0]
0x1400041fc  add     rsp, 30h
0x140004200  pop     rdi
0x140004201  retn
```
