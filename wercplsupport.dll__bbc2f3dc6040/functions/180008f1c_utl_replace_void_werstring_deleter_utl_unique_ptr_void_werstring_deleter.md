# utl::replace<void,werstring_deleter>(utl::unique_ptr<void,werstring_deleter> &)

- ea: `0x180008f1c`
- end: `0x180008f4d`
- name: `??$replace@XUwerstring_deleter@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XUwerstring_deleter@@@0@@Z`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ef80`
- `0x18000fd54`
- `0x18000fef4`
- `0x180010734`

## callees

- `0x180008f1c`

## import_xrefs

- `wer!WerpDestroyWerString` at `0x180008f3e`
- `wer!WerpDestroyWerString` at `0x180008f3e`

## pseudocode

```c
__int64 *__fastcall utl::replace<void,werstring_deleter>(__int64 *a1)
{
  __int64 v1; // rax
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    v4 = v1;
    WerpDestroyWerString(&v4);
  }
  return a1;
}

```

## disassembly

```asm
0x180008f1c  push    rbx
0x180008f1e  sub     rsp, 20h
0x180008f22  mov     rax, [rcx]
0x180008f25  mov     rbx, rcx
0x180008f28  mov     qword ptr [rcx], 0
0x180008f2f  test    rax, rax
0x180008f32  jz      short loc_180008F44
0x180008f34  lea     rcx, [rsp+28h+arg_0]
0x180008f39  mov     [rsp+28h+arg_0], rax
0x180008f3e  call    cs:__imp_WerpDestroyWerString
0x180008f44  mov     rax, rbx
0x180008f47  add     rsp, 20h
0x180008f4b  pop     rbx
0x180008f4c  retn
```
