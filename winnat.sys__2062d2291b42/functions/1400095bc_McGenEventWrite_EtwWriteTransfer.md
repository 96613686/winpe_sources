# McGenEventWrite_EtwWriteTransfer

- ea: `0x1400095bc`
- end: `0x140009614`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `88`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400093f0`
- `0x14000d7c8`
- `0x14000e3e8`
- `0x14000e4b0`
- `0x14000e538`
- `0x14000e6a8`
- `0x14000e790`
- `0x140014480`
- `0x140014548`
- `0x1400146b0`
- `0x140014830`
- `0x1400148fc`
- `0x1400149bc`
- `0x14001567c`
- `0x140016f08`
- `0x140019d64`
- `0x140019e38`
- `0x14001af88`
- `0x14001b050`
- `0x14001bf40`

## callees

- `0x1400095bc`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x1400095f3`
- `ntoskrnl!EtwWriteTransfer` at `0x1400095f3`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
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
  return EtwWriteTransfer(*a1, a2, &MICROSOFT_WINNAT_ETW_PROVIDER, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1400095bc  sub     rsp, 38h
0x1400095c0  mov     r8, [rcx+8]
0x1400095c4  mov     rax, [rsp+38h+arg_20]
0x1400095c9  test    r8, r8
0x1400095cc  jnz     short loc_140009605
0x1400095ce  mov     [rax], r8
0x1400095d1  xor     r10d, r10d
0x1400095d4  mov     [rax+8], r8d
0x1400095d8  lea     r8, MICROSOFT_WINNAT_ETW_PROVIDER; ActivityId
0x1400095df  mov     [rsp+38h+UserData], rax; UserData
0x1400095e4  mov     [rax+0Ch], r10d
0x1400095e8  mov     rcx, [rcx]; RegHandle
0x1400095eb  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1400095f0  xor     r9d, r9d; RelatedActivityId
0x1400095f3  call    cs:__imp_EtwWriteTransfer
0x1400095fa  nop     dword ptr [rax+rax+00h]
0x1400095ff  add     rsp, 38h
0x140009603  retn
0x140009605  mov     [rax], r8
0x140009608  mov     r10d, 2
0x14000960e  movzx   r8d, word ptr [r8]
0x140009612  jmp     short loc_1400095D4
```
