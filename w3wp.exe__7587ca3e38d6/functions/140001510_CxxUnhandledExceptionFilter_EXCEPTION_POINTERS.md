# __CxxUnhandledExceptionFilter(_EXCEPTION_POINTERS *)

- ea: `0x140001510`
- end: `0x140001549`
- name: `?__CxxUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z`
- size: `57`
- prototype: `LONG __stdcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001510`

## import_xrefs

- `msvcrt!?terminate@@YAXXZ` at `0x14000153b`
- `msvcrt!?terminate@@YAXXZ` at `0x14000153b`

## pseudocode

```c
__int64 __fastcall __CxxUnhandledExceptionFilter(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  PEXCEPTION_RECORD ExceptionRecord; // rax
  int v2; // ecx

  ExceptionRecord = ExceptionInfo->ExceptionRecord;
  if ( ExceptionInfo->ExceptionRecord->ExceptionCode == -529697949 && ExceptionRecord->NumberParameters == 4 )
  {
    v2 = ExceptionRecord->ExceptionInformation[0];
    if ( (unsigned int)(v2 - 429065504) <= 2 || v2 == 26820608 )
      terminate();
  }
  return 0;
}

```

## disassembly

```asm
0x140001510  sub     rsp, 28h
0x140001514  mov     rax, [rcx]
0x140001517  cmp     dword ptr [rax], 0E06D7363h
0x14000151d  jnz     short loc_140001542
0x14000151f  cmp     dword ptr [rax+18h], 4
0x140001523  jnz     short loc_140001542
0x140001525  mov     ecx, [rax+20h]
0x140001528  lea     eax, [rcx-19930520h]
0x14000152e  cmp     eax, 2
0x140001531  jbe     short loc_14000153B
0x140001533  cmp     ecx, 1994000h
0x140001539  jnz     short loc_140001542
0x14000153b  call    cs:__imp_?terminate@@YAXXZ; terminate(void)
0x140001542  xor     eax, eax
0x140001544  add     rsp, 28h
0x140001548  retn
```
