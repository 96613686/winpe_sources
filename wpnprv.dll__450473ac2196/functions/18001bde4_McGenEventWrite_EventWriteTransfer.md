# McGenEventWrite_EventWriteTransfer

- ea: `0x18001bde4`
- end: `0x18001be31`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `42`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b940`
- `0x18001be38`
- `0x1800279a0`
- `0x18002f27c`
- `0x18002f2d8`
- `0x18002f348`
- `0x18002f3c8`
- `0x180031d7c`
- `0x180031dec`
- `0x180043608`
- `0x1800454ec`
- `0x18004b8b8`
- `0x18004e45c`
- `0x1800592b4`
- `0x18005b734`
- `0x18005f7c8`
- `0x18005f868`
- `0x18005f914`
- `0x1800634e8`
- `0x1800635c4`
- `0x18006cd00`
- `0x18006f460`
- `0x180070300`
- `0x180071d08`
- `0x180075bac`
- `0x180075d18`
- `0x180075dec`
- `0x180075e90`
- `0x180075f80`
- `0x180076080`
- `0x180076190`
- `0x1800762c8`
- `0x1800763f4`
- `0x1800764dc`
- `0x1800765f4`
- `0x18007669c`
- `0x180089100`
- `0x18008b640`
- `0x18008cd44`
- `0x18008d360`
- `0x18008fb88`
- `0x180090030`

## callees

- `0x18001bde4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001be26`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001be26`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EventWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18001bde4  sub     rsp, 38h
0x18001bde8  mov     r8, [rcx+8]
0x18001bdec  mov     rax, [rsp+38h+arg_20]
0x18001bdf1  test    r8, r8
0x18001bdf4  jnz     short loc_18001BDFE
0x18001bdf6  mov     [rax], r8
0x18001bdf9  xor     r10d, r10d
0x18001bdfc  jmp     short loc_18001BE0B
0x18001bdfe  mov     [rax], r8
0x18001be01  mov     r10d, 2
0x18001be07  movzx   r8d, word ptr [r8]
0x18001be0b  mov     [rax+8], r8d
0x18001be0f  xor     r8d, r8d; ActivityId
0x18001be12  mov     [rsp+38h+UserData], rax; UserData
0x18001be17  mov     [rax+0Ch], r10d
0x18001be1b  mov     rcx, [rcx]; RegHandle
0x18001be1e  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18001be23  xor     r9d, r9d; RelatedActivityId
0x18001be26  call    cs:__imp_EventWriteTransfer
0x18001be2c  add     rsp, 38h
0x18001be30  retn
```
