# McGenEventWrite_EventWriteTransfer

- ea: `0x18000247c`
- end: `0x1800024ce`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `32`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180003d30`
- `0x180003dc8`
- `0x180003e60`
- `0x180003f00`
- `0x1800052f4`
- `0x1800053c0`
- `0x180005468`
- `0x1800067c0`
- `0x180006950`
- `0x180006cd0`
- `0x180006fa0`
- `0x180007c88`
- `0x180007ce0`
- `0x180007d60`
- `0x180009604`
- `0x18000ab30`
- `0x18000ad80`
- `0x18000b1f8`
- `0x18000b268`
- `0x18000b324`
- `0x18000b3f8`
- `0x18000b4f8`
- `0x18000b5fc`
- `0x18000d030`
- `0x18000d100`
- `0x180010938`
- `0x180011984`
- `0x180011aa8`
- `0x1800124a8`

## callees

- `0x18000247c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800024c3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800024c3`

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

  v5 = (unsigned __int16 *)qword_180023068;
  if ( qword_180023068 )
  {
    UserData->Ptr = qword_180023068;
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
  return EventWriteTransfer(SDIAGPRV_PROVIDER_GUID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000247c  sub     rsp, 38h
0x180002480  mov     rcx, cs:qword_180023068
0x180002487  mov     rax, [rsp+38h+arg_20]
0x18000248c  test    rcx, rcx
0x18000248f  jnz     short loc_180002499
0x180002491  mov     [rax], rcx
0x180002494  xor     r8d, r8d
0x180002497  jmp     short loc_1800024A5
0x180002499  mov     [rax], rcx
0x18000249c  mov     r8d, 2
0x1800024a2  movzx   ecx, word ptr [rcx]
0x1800024a5  mov     [rax+8], ecx
0x1800024a8  mov     [rax+0Ch], r8d
0x1800024ac  xor     r8d, r8d; ActivityId
0x1800024af  mov     rcx, cs:SDIAGPRV_PROVIDER_GUID_Context; RegHandle
0x1800024b6  mov     [rsp+38h+UserData], rax; UserData
0x1800024bb  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800024c0  xor     r9d, r9d; RelatedActivityId
0x1800024c3  call    cs:__imp_EventWriteTransfer
0x1800024c9  add     rsp, 38h
0x1800024cd  retn
```
