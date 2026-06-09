# CTrayClock::HideFlyout(void)

- ea: `0x18001f1e0`
- end: `0x18001f20f`
- name: `?HideFlyout@CTrayClock@@UEAAJXZ`
- size: `47`
- prototype: `__int64 __fastcall(CTrayClock *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180016e28`
- `0x18001f1e0`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x18001f1f5`
- `USER32!PostThreadMessageW` at `0x18001f1f5`

## pseudocode

```c
__int64 __fastcall CTrayClock::HideFlyout(CTrayClock *this)
{
  DWORD v1; // ecx

  v1 = *((_DWORD *)this + 17);
  if ( !v1 || PostThreadMessageW(v1, 0x12u, 0, 0) )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x18001f1e0  sub     rsp, 28h
0x18001f1e4  mov     ecx, [rcx+44h]; idThread
0x18001f1e7  test    ecx, ecx
0x18001f1e9  jz      short loc_18001F208
0x18001f1eb  xor     r9d, r9d; lParam
0x18001f1ee  xor     r8d, r8d; wParam
0x18001f1f1  lea     edx, [r9+12h]; Msg
0x18001f1f5  call    cs:__imp_PostThreadMessageW
0x18001f1fb  test    eax, eax
0x18001f1fd  jnz     short loc_18001F208
0x18001f1ff  add     rsp, 28h
0x18001f203  jmp     ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001f208  xor     eax, eax
0x18001f20a  add     rsp, 28h
0x18001f20e  retn
```
