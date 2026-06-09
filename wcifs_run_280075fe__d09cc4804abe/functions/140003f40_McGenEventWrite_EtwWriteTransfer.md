# McGenEventWrite_EtwWriteTransfer

- ea: `0x140003f40`
- end: `0x140003f99`
- name: `McGenEventWrite_EtwWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003274`
- `0x14000672c`
- `0x14000678c`

## callees

- `0x140003f40`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x140003f87`
- `ntoskrnl!EtwWriteTransfer` at `0x140003f87`

## pseudocode

```c
NTSTATUS __fastcall McGenEventWrite_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_14000E018;
  if ( qword_14000E018 )
  {
    UserData->Ptr = qword_14000E018;
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
  return EtwWriteTransfer(PROV_WCIFS_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140003f40  sub     rsp, 38h
0x140003f44  mov     rcx, cs:qword_14000E018
0x140003f4b  mov     rax, [rsp+38h+arg_20]
0x140003f50  test    rcx, rcx
0x140003f53  jnz     short loc_140003F5D
0x140003f55  mov     [rax], rcx
0x140003f58  xor     r8d, r8d
0x140003f5b  jmp     short loc_140003F69
0x140003f5d  mov     [rax], rcx
0x140003f60  mov     r8d, 2
0x140003f66  movzx   ecx, word ptr [rcx]
0x140003f69  mov     [rax+8], ecx
0x140003f6c  mov     [rax+0Ch], r8d
0x140003f70  xor     r8d, r8d; ActivityId
0x140003f73  mov     rcx, cs:PROV_WCIFS_Context; RegHandle
0x140003f7a  mov     [rsp+38h+UserData], rax; UserData
0x140003f7f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140003f84  xor     r9d, r9d; RelatedActivityId
0x140003f87  call    cs:__imp_EtwWriteTransfer
0x140003f8e  nop     dword ptr [rax+rax+00h]
0x140003f93  add     rsp, 38h
0x140003f97  retn
```
