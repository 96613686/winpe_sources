# WARMUP_APPLICATION_CONTEXT::CreateWarmupApplicationContext(ushort const *,ushort const *,int)

- ea: `0x1800047c0`
- end: `0x180004804`
- name: `?CreateWarmupApplicationContext@WARMUP_APPLICATION_CONTEXT@@UEAAJPEBG0H@Z`
- size: `68`
- prototype: `int __fastcall(WARMUP_APPLICATION_CONTEXT *this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800047c0`

## import_xrefs

- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800047ec`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800047ec`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800047db`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800047db`

## pseudocode

```c
int __fastcall WARMUP_APPLICATION_CONTEXT::CreateWarmupApplicationContext(
        WARMUP_APPLICATION_CONTEXT *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  int result; // eax

  if ( !a3
    || (result = STRU::Copy((WARMUP_APPLICATION_CONTEXT *)((char *)this + 24), a2), result >= 0)
    && (result = STRU::Append((WARMUP_APPLICATION_CONTEXT *)((char *)this + 24), a3), result >= 0) )
  {
    *((_DWORD *)this + 20) = a4;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800047c0  push    rbx
0x1800047c2  push    rbp
0x1800047c3  push    rsi
0x1800047c4  push    rdi
0x1800047c5  sub     rsp, 28h
0x1800047c9  mov     edi, r9d
0x1800047cc  mov     rsi, r8
0x1800047cf  mov     rbx, rcx
0x1800047d2  test    r8, r8
0x1800047d5  jz      short loc_1800047F6
0x1800047d7  add     rcx, 18h
0x1800047db  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800047e1  test    eax, eax
0x1800047e3  js      short loc_1800047FB
0x1800047e5  mov     rdx, rsi
0x1800047e8  lea     rcx, [rbx+18h]
0x1800047ec  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800047f2  test    eax, eax
0x1800047f4  js      short loc_1800047FB
0x1800047f6  mov     [rbx+50h], edi
0x1800047f9  xor     eax, eax
0x1800047fb  add     rsp, 28h
0x1800047ff  pop     rdi
0x180004800  pop     rsi
0x180004801  pop     rbp
0x180004802  pop     rbx
0x180004803  retn
```
