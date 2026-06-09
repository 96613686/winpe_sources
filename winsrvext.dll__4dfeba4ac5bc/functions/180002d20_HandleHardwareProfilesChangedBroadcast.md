# HandleHardwareProfilesChangedBroadcast

- ea: `0x180002d20`
- end: `0x180002e16`
- name: `HandleHardwareProfilesChangedBroadcast`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002230`

## callees

- `0x180002d20`

## import_xrefs

- `win32u!NtUserSetInformationThread` at `0x180002db5`
- `win32u!NtUserSetInformationThread` at `0x180002e03`
- `win32u!NtUserSetInformationThread` at `0x180002db5`
- `win32u!NtUserSetInformationThread` at `0x180002e03`
- `USER32!BroadcastSystemMessageW` at `0x180002de1`
- `USER32!BroadcastSystemMessageW` at `0x180002de1`

## pseudocode

```c
__int64 __fastcall HandleHardwareProfilesChangedBroadcast(__int64 *a1)
{
  bool v1; // zf
  WPARAM v2; // rbx
  __int64 result; // rax
  __int128 v4; // [rsp+30h] [rbp-28h] BYREF
  __int64 v5; // [rsp+40h] [rbp-18h]
  DWORD Info; // [rsp+68h] [rbp+10h] BYREF

  v5 = 0;
  v1 = *a1 == *(_QWORD *)&GUID_HWPROFILE_QUERY_CHANGE.Data1;
  v4 = 0;
  if ( v1 && a1[1] == *(_QWORD *)GUID_HWPROFILE_QUERY_CHANGE.Data4 )
  {
    v2 = 23;
    goto LABEL_10;
  }
  if ( *a1 == *(_QWORD *)&GUID_HWPROFILE_CHANGE_CANCELLED.Data1
    && a1[1] == *(_QWORD *)GUID_HWPROFILE_CHANGE_CANCELLED.Data4 )
  {
    v2 = 25;
    goto LABEL_10;
  }
  result = *a1;
  if ( *a1 == *(_QWORD *)&GUID_HWPROFILE_CHANGE_COMPLETE.Data1 )
  {
    result = a1[1];
    if ( result == *(_QWORD *)GUID_HWPROFILE_CHANGE_COMPLETE.Data4 )
    {
      v2 = 24;
LABEL_10:
      Info = 16;
      result = NtUserSetInformationThread(-2, 7, &v4);
      if ( (int)result >= 0 )
      {
        BroadcastSystemMessageW(0x20000000u, &Info, 0x219u, v2, 0);
        return NtUserSetInformationThread(-2, 9, &v4);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002d20  push    rbx
0x180002d22  sub     rsp, 50h
0x180002d26  xor     eax, eax
0x180002d28  xorps   xmm0, xmm0
0x180002d2b  mov     [rsp+58h+var_18], rax
0x180002d30  mov     rax, [rcx]
0x180002d33  cmp     rax, qword ptr cs:GUID_HWPROFILE_QUERY_CHANGE.Data1
0x180002d3a  movups  [rsp+58h+var_28], xmm0
0x180002d3f  jnz     short loc_180002D55
0x180002d41  mov     rax, [rcx+8]
0x180002d45  cmp     rax, qword ptr cs:GUID_HWPROFILE_QUERY_CHANGE.Data4
0x180002d4c  jnz     short loc_180002D55
0x180002d4e  mov     ebx, 17h
0x180002d53  jmp     short loc_180002D97
0x180002d55  mov     rax, [rcx]
0x180002d58  cmp     rax, qword ptr cs:GUID_HWPROFILE_CHANGE_CANCELLED.Data1
0x180002d5f  jnz     short loc_180002D75
0x180002d61  mov     rax, [rcx+8]
0x180002d65  cmp     rax, qword ptr cs:GUID_HWPROFILE_CHANGE_CANCELLED.Data4
0x180002d6c  jnz     short loc_180002D75
0x180002d6e  mov     ebx, 19h
0x180002d73  jmp     short loc_180002D97
0x180002d75  mov     rax, [rcx]
0x180002d78  cmp     rax, qword ptr cs:GUID_HWPROFILE_CHANGE_COMPLETE.Data1
0x180002d7f  jnz     loc_180002E0F
0x180002d85  mov     rax, [rcx+8]
0x180002d89  cmp     rax, qword ptr cs:GUID_HWPROFILE_CHANGE_COMPLETE.Data4
0x180002d90  jnz     short loc_180002E0F
0x180002d92  mov     ebx, 18h
0x180002d97  mov     r9d, 18h
0x180002d9d  mov     [rsp+58h+Info], 10h
0x180002da5  lea     r8, [rsp+58h+var_28]
0x180002daa  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180002db1  lea     edx, [r9-11h]
0x180002db5  call    cs:__imp_NtUserSetInformationThread
0x180002dbc  nop     dword ptr [rax+rax+00h]
0x180002dc1  test    eax, eax
0x180002dc3  js      short loc_180002E0F
0x180002dc5  mov     r9, rbx; wParam
0x180002dc8  mov     [rsp+58h+lParam], 0; lParam
0x180002dd1  mov     r8d, 219h; Msg
0x180002dd7  lea     rdx, [rsp+58h+Info]; lpInfo
0x180002ddc  mov     ecx, 20000000h; flags
0x180002de1  call    cs:__imp_BroadcastSystemMessageW
0x180002de8  nop     dword ptr [rax+rax+00h]
0x180002ded  mov     r9d, 18h
0x180002df3  lea     r8, [rsp+58h+var_28]
0x180002df8  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180002dff  lea     edx, [r9-0Fh]
0x180002e03  call    cs:__imp_NtUserSetInformationThread
0x180002e0a  nop     dword ptr [rax+rax+00h]
0x180002e0f  add     rsp, 50h
0x180002e13  pop     rbx
0x180002e14  retn
```
