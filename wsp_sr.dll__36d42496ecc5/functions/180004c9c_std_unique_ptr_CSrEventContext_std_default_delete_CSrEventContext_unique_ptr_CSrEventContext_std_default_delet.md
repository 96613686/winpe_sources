# std::unique_ptr<CSrEventContext,std::default_delete<CSrEventContext>>::~unique_ptr<CSrEventContext,std::default_delete<CSrEventContext>>(void)

- ea: `0x180004c9c`
- end: `0x180004cb2`
- name: `??1?$unique_ptr@VCSrEventContext@@U?$default_delete@VCSrEventContext@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180004df0`
- `0x180004e80`
- `0x180005080`
- `0x180005110`
- `0x180005310`
- `0x1800053a0`
- `0x18002c4e0`
- `0x18002c500`
- `0x18002c520`

## callees

- `0x180004c9c`
- `0x180004cfc`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<CSrEventContext>::~unique_ptr<CSrEventContext>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<CSrEventContext>::operator()();
  return result;
}

```

## disassembly

```asm
0x180004c9c  sub     rsp, 28h
0x180004ca0  mov     rdx, [rcx]
0x180004ca3  test    rdx, rdx
0x180004ca6  jz      short loc_180004CAD
0x180004ca8  call    ??R?$default_delete@VCSrEventContext@@@std@@QEBAXPEAVCSrEventContext@@@Z; std::default_delete<CSrEventContext>::operator()(CSrEventContext *)
0x180004cad  add     rsp, 28h
0x180004cb1  retn
```
