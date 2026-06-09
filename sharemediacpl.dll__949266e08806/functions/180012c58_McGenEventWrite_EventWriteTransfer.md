# McGenEventWrite_EventWriteTransfer

- ea: `0x180012c58`
- end: `0x180012caa`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a9f0`
- `0x18000d1e4`
- `0x18000ec90`
- `0x18000f020`
- `0x18000f1cc`
- `0x18000fbd0`
- `0x18000fd88`
- `0x180010590`
- `0x180010914`
- `0x180010bec`
- `0x180011390`
- `0x1800125c0`
- `0x180012cb0`
- `0x180013490`

## callees

- `0x180012c58`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180012c9f`
- `ADVAPI32!EventWriteTransfer` at `0x180012c9f`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_18002A018;
  if ( qword_18002A018 )
  {
    UserData->Ptr = qword_18002A018;
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
  return EventWriteTransfer(SHAREMEDIACPL_EVENT_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180012c58  sub     rsp, 38h
0x180012c5c  mov     rcx, cs:qword_18002A018
0x180012c63  mov     rax, [rsp+38h+arg_20]
0x180012c68  test    rcx, rcx
0x180012c6b  jnz     short loc_180012C75
0x180012c6d  mov     [rax], rcx
0x180012c70  xor     r8d, r8d
0x180012c73  jmp     short loc_180012C81
0x180012c75  mov     [rax], rcx
0x180012c78  mov     r8d, 2
0x180012c7e  movzx   ecx, word ptr [rcx]
0x180012c81  mov     [rax+8], ecx
0x180012c84  mov     [rax+0Ch], r8d
0x180012c88  xor     r8d, r8d; ActivityId
0x180012c8b  mov     rcx, cs:SHAREMEDIACPL_EVENT_Context; RegHandle
0x180012c92  mov     [rsp+38h+UserData], rax; UserData
0x180012c97  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180012c9c  xor     r9d, r9d; RelatedActivityId
0x180012c9f  call    cs:__imp_EventWriteTransfer
0x180012ca5  add     rsp, 38h
0x180012ca9  retn
```
