# SubscriptionConfigReader::GetEnabled(bool &)

- ea: `0x180004288`
- end: `0x1800042c8`
- name: `?GetEnabled@SubscriptionConfigReader@@QEBA_NAEA_N@Z`
- size: `64`
- prototype: `char __fastcall(SubscriptionConfigReader *this, bool *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004760`
- `0x1800052cc`
- `0x18001483c`
- `0x1800165c0`

## callees

- `0x180004288`
- `0x180012424`

## pseudocode

```c
char __fastcall SubscriptionConfigReader::GetEnabled(SubscriptionConfigReader *this, bool *a2)
{
  HKEY v2; // rcx
  unsigned int v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = (HKEY)*((_QWORD *)this + 2);
  v5 = 0;
  if ( !RegReadDWORDValue(v2, L"Enabled", &v5) )
    return 0;
  *a2 = v5 != 0;
  return 1;
}

```

## disassembly

```asm
0x180004288  push    rbx
0x18000428a  sub     rsp, 20h
0x18000428e  mov     rcx, [rcx+10h]; HKEY
0x180004292  lea     r8, [rsp+28h+arg_0]; unsigned int *
0x180004297  mov     rbx, rdx
0x18000429a  mov     [rsp+28h+arg_0], 0
0x1800042a2  lea     rdx, aEnabled; "Enabled"
0x1800042a9  call    ?RegReadDWORDValue@@YA_NPEAUHKEY__@@PEBGAEAK@Z; RegReadDWORDValue(HKEY__ *,ushort const *,ulong &)
0x1800042ae  test    al, al
0x1800042b0  jz      short loc_1800042C0
0x1800042b2  cmp     [rsp+28h+arg_0], 0
0x1800042b7  setnz   al
0x1800042ba  mov     [rbx], al
0x1800042bc  mov     al, 1
0x1800042be  jmp     short loc_1800042C2
0x1800042c0  xor     al, al
0x1800042c2  add     rsp, 20h
0x1800042c6  pop     rbx
0x1800042c7  retn
```
