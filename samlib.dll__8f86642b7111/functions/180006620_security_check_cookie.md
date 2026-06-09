# __security_check_cookie

- ea: `0x180006620`
- end: `0x18000663e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `54`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002530`
- `0x1800040e0`
- `0x180004dd0`
- `0x180005500`
- `0x180005630`
- `0x1800059a0`
- `0x180006160`
- `0x1800079c8`
- `0x180007e00`
- `0x180008250`
- `0x1800083a0`
- `0x180008830`
- `0x18000918c`
- `0x180009a34`
- `0x180009b38`
- `0x180009fe8`
- `0x18000a10c`
- `0x18000a310`
- `0x18000a5a0`
- `0x18000ab74`
- `0x18000b3b4`
- `0x18000b6ec`
- `0x18000ba10`
- `0x18000ba68`
- `0x18000baf8`
- `0x18000bb64`
- `0x18000bbe0`
- `0x18000bc7c`
- `0x18000bd18`
- `0x18000bde4`
- `0x18000bed0`
- `0x18000bfa8`
- `0x18000c070`
- `0x18000c120`
- `0x18000c210`
- `0x18000c2a8`
- `0x18000c39c`
- `0x18000c480`
- `0x18000c554`
- `0x18000ccb0`
- `0x18000d020`
- `0x1800127a0`
- `0x180012c30`
- `0x180013490`
- `0x1800152bc`
- `0x1800153a8`
- `0x180015b44`
- `0x1800160d8`
- `0x1800163d0`
- `0x18001672c`

## callees

- `0x180006620`
- `0x180006b50`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180006620  cmp     rcx, cs:__security_cookie
0x180006627  jnz     short ReportFailure
0x180006629  rol     rcx, 10h
0x18000662d  test    cx, 0FFFFh
0x180006632  jnz     short RestoreRcx
0x180006634  retn
0x180006635  ror     rcx, 10h; StackCookie
0x180006639  jmp     __report_gsfailure
```
