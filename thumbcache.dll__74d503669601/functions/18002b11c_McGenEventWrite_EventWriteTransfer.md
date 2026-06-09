# McGenEventWrite_EventWriteTransfer

- ea: `0x18002b11c`
- end: `0x18002b16e`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `23`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003aec`
- `0x180008a70`
- `0x18000cc10`
- `0x18001161c`
- `0x18001195c`
- `0x180011c10`
- `0x180013d80`
- `0x180014ae0`
- `0x180015868`
- `0x1800249d0`
- `0x18002acdc`
- `0x18002afc8`
- `0x18002b024`
- `0x18002b07c`
- `0x18002cc40`
- `0x18002d090`
- `0x18002f0e8`
- `0x18003a980`
- `0x1800429b4`
- `0x180043904`
- `0x1800439b0`
- `0x1800443fc`
- `0x180044f84`

## callees

- `0x18002b11c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002b155`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002b155`

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

  v5 = (unsigned __int16 *)qword_180062048;
  if ( qword_180062048 )
  {
    UserData->Ptr = qword_180062048;
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
  return EventWriteTransfer(Microsoft_Windows_Shell_Core_Provider_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18002b11c  sub     rsp, 38h
0x18002b120  mov     rcx, cs:qword_180062048
0x18002b127  mov     rax, [rsp+38h+arg_20]
0x18002b12c  test    rcx, rcx
0x18002b12f  jnz     short loc_18002B160
0x18002b131  mov     [rax], rcx
0x18002b134  xor     r8d, r8d
0x18002b137  mov     [rax+8], ecx
0x18002b13a  mov     [rax+0Ch], r8d
0x18002b13e  xor     r8d, r8d; ActivityId
0x18002b141  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context; RegHandle
0x18002b148  mov     [rsp+38h+UserData], rax; UserData
0x18002b14d  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18002b152  xor     r9d, r9d; RelatedActivityId
0x18002b155  call    cs:__imp_EventWriteTransfer
0x18002b15b  add     rsp, 38h
0x18002b15f  retn
0x18002b160  mov     [rax], rcx
0x18002b163  mov     r8d, 2
0x18002b169  movzx   ecx, word ptr [rcx]
0x18002b16c  jmp     short loc_18002B137
```
