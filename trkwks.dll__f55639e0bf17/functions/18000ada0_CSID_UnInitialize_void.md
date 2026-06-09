# CSID::UnInitialize(void)

- ea: `0x18000ada0`
- end: `0x18000adc9`
- name: `?UnInitialize@CSID@@QEAAXXZ`
- size: `41`
- prototype: `void __fastcall(CSID *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a65c`
- `0x18000a880`
- `0x18000ad70`
- `0x18000d1a0`
- `0x180010638`

## callees

- `0x18000ada0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000adb7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000adb7`

## pseudocode

```c
void __fastcall CSID::UnInitialize(CSID *this)
{
  void *v2; // rcx

  if ( *(_DWORD *)this )
  {
    v2 = (void *)*((_QWORD *)this + 1);
    if ( v2 )
      FreeSid(v2);
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000ada0  push    rbx
0x18000ada2  sub     rsp, 20h
0x18000ada6  cmp     dword ptr [rcx], 0
0x18000ada9  mov     rbx, rcx
0x18000adac  jz      short loc_18000ADC3
0x18000adae  mov     rcx, [rcx+8]; pSid
0x18000adb2  test    rcx, rcx
0x18000adb5  jz      short loc_18000ADBD
0x18000adb7  call    cs:__imp_FreeSid
0x18000adbd  mov     dword ptr [rbx], 0
0x18000adc3  add     rsp, 20h
0x18000adc7  pop     rbx
0x18000adc8  retn
```
