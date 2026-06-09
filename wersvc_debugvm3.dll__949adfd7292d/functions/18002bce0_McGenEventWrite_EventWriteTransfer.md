# McGenEventWrite_EventWriteTransfer

- ea: `0x18002bce0`
- end: `0x18002bd39`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002bd40`

## callees

- `0x18002bce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002bd2e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002bd2e`

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

  v5 = (unsigned __int16 *)qword_180047048;
  if ( qword_180047048 )
  {
    UserData->Ptr = qword_180047048;
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
  return EventWriteTransfer(EventProviderApplication_Hang_Context, &ApplicationHang, 0, 0, 0xBu, UserData);
}

```

## disassembly

```asm
0x18002bce0  sub     rsp, 38h
0x18002bce4  mov     rcx, cs:qword_180047048
0x18002bceb  mov     rax, [rsp+38h+arg_20]
0x18002bcf0  test    rcx, rcx
0x18002bcf3  jnz     short loc_18002BCFC
0x18002bcf5  mov     [rax], rcx
0x18002bcf8  xor     edx, edx
0x18002bcfa  jmp     short loc_18002BD07
0x18002bcfc  mov     [rax], rcx
0x18002bcff  mov     edx, 2
0x18002bd04  movzx   ecx, word ptr [rcx]
0x18002bd07  mov     [rax+8], ecx
0x18002bd0a  xor     r9d, r9d; RelatedActivityId
0x18002bd0d  mov     [rax+0Ch], edx
0x18002bd10  xor     r8d, r8d; ActivityId
0x18002bd13  mov     rcx, cs:EventProviderApplication_Hang_Context; RegHandle
0x18002bd1a  lea     rdx, ApplicationHang; EventDescriptor
0x18002bd21  mov     [rsp+38h+UserData], rax; UserData
0x18002bd26  mov     [rsp+38h+UserDataCount], 0Bh; UserDataCount
0x18002bd2e  call    cs:__imp_EventWriteTransfer
0x18002bd34  add     rsp, 38h
0x18002bd38  retn
```
