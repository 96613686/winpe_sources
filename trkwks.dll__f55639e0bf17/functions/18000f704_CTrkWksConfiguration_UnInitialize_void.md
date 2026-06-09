# CTrkWksConfiguration::UnInitialize(void)

- ea: `0x18000f704`
- end: `0x18000f722`
- name: `?UnInitialize@CTrkWksConfiguration@@QEAAXXZ`
- size: `30`
- prototype: `void __fastcall(CTrkWksConfiguration *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001e28`
- `0x18000ef2c`

## callees

- `0x180007440`
- `0x18000f704`

## pseudocode

```c
void __fastcall CTrkWksConfiguration::UnInitialize(CTrkWksConfiguration *this)
{
  if ( (*((_BYTE *)this + 32) & 1) != 0 )
  {
    CTrkConfiguration::UnInitialize(this);
    *((_DWORD *)this + 8) &= ~1u;
  }
}

```

## disassembly

```asm
0x18000f704  push    rbx
0x18000f706  sub     rsp, 20h
0x18000f70a  test    byte ptr [rcx+20h], 1
0x18000f70e  mov     rbx, rcx
0x18000f711  jz      short loc_18000F71C
0x18000f713  call    ?UnInitialize@CTrkConfiguration@@QEAAXXZ; CTrkConfiguration::UnInitialize(void)
0x18000f718  and     dword ptr [rbx+20h], 0FFFFFFFEh
0x18000f71c  add     rsp, 20h
0x18000f720  pop     rbx
0x18000f721  retn
```
