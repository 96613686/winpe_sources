# McGenEventWrite_EventWriteTransfer

- ea: `0x180011778`
- end: `0x1800117d1`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010300`

## callees

- `0x180011778`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800117c6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800117c6`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // edx

  v5 = (unsigned __int16 *)qword_18003F568;
  if ( qword_18003F568 )
  {
    UserData->Ptr = qword_18003F568;
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
  return EventWriteTransfer(Microsoft_Windows_WlanPref_Context, &NSC_WLANPREF, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x180011778  sub     rsp, 38h
0x18001177c  mov     rcx, cs:qword_18003F568
0x180011783  mov     rax, [rsp+38h+arg_20]
0x180011788  test    rcx, rcx
0x18001178b  jnz     short loc_180011794
0x18001178d  mov     [rax], rcx
0x180011790  xor     edx, edx
0x180011792  jmp     short loc_18001179F
0x180011794  mov     [rax], rcx
0x180011797  mov     edx, 2
0x18001179c  movzx   ecx, word ptr [rcx]
0x18001179f  mov     [rax+8], ecx
0x1800117a2  xor     r9d, r9d; RelatedActivityId
0x1800117a5  mov     [rax+0Ch], edx
0x1800117a8  xor     r8d, r8d; ActivityId
0x1800117ab  mov     rcx, cs:Microsoft_Windows_WlanPref_Context; RegHandle
0x1800117b2  lea     rdx, NSC_WLANPREF; EventDescriptor
0x1800117b9  mov     [rsp+38h+UserData], rax; UserData
0x1800117be  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x1800117c6  call    cs:__imp_EventWriteTransfer
0x1800117cc  add     rsp, 38h
0x1800117d0  retn
```
