# LogApplicationSettingQuery

- ea: `0x180034164`
- end: `0x1800342cb`
- name: `LogApplicationSettingQuery`
- size: `359`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180033778`
- `0x1800339f8`
- `0x180033d40`

## callees

- `0x180021ec0`
- `0x180034164`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800342a6`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800342a6`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800341b5`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800341b5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180034291`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180034291`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ULONG LogApplicationSettingQuery(__int64 a1, __int64 a2, int a3, ...)
{
  ULONG result; // eax
  const EVENT_DESCRIPTOR *v6; // rdx
  ULONG UserDataCount; // eax
  ULONGLONG RegHandle[2]; // [rsp+40h] [rbp-79h] BYREF
  char v9; // [rsp+50h] [rbp-69h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-61h] BYREF
  __int64 v11; // [rsp+68h] [rbp-51h]
  int v12; // [rsp+70h] [rbp-49h]
  int v13; // [rsp+74h] [rbp-45h]
  int *v14; // [rsp+78h] [rbp-41h]
  __int64 v15; // [rsp+80h] [rbp-39h]
  va_list v16; // [rsp+88h] [rbp-31h]
  __int64 v17; // [rsp+90h] [rbp-29h]
  __int64 v18; // [rsp+98h] [rbp-21h]
  int v19; // [rsp+A0h] [rbp-19h]
  int v20; // [rsp+A4h] [rbp-15h]
  va_list v21; // [rsp+A8h] [rbp-11h]
  __int64 v22; // [rsp+B0h] [rbp-9h]
  __int64 v23; // [rsp+B8h] [rbp-1h]
  int v24; // [rsp+C0h] [rbp+7h]
  int v25; // [rsp+C4h] [rbp+Bh]
  int v26; // [rsp+108h] [rbp+4Fh] BYREF
  __int64 v27; // [rsp+110h] [rbp+57h] BYREF
  va_list va; // [rsp+110h] [rbp+57h]
  __int64 v29; // [rsp+118h] [rbp+5Fh]
  __int64 v30; // [rsp+120h] [rbp+67h]
  __int64 v31; // [rsp+128h] [rbp+6Fh] BYREF
  va_list va1; // [rsp+128h] [rbp+6Fh]
  __int64 v33; // [rsp+130h] [rbp+77h]
  __int64 v34; // [rsp+138h] [rbp+7Fh]
  va_list va2; // [rsp+140h] [rbp+87h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v27 = va_arg(va1, _QWORD);
  v29 = va_arg(va1, _QWORD);
  v30 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v31 = va_arg(va2, _QWORD);
  v33 = va_arg(va2, _QWORD);
  v34 = va_arg(va2, _QWORD);
  v26 = a3;
  RegHandle[0] = 0;
  result = EventRegister(&SrpEventProviderId, 0, 0, RegHandle);
  if ( !result )
  {
    RegHandle[1] = (ULONGLONG)RegHandle;
    v9 = 1;
    UserData.Ptr = *(_QWORD *)(a1 + 8);
    UserData.Size = *(unsigned __int16 *)(a1 + 2);
    UserData.Reserved = 0;
    v11 = *(_QWORD *)(a2 + 8);
    v12 = *(unsigned __int16 *)(a2 + 2);
    v13 = 0;
    v14 = &v26;
    v15 = 4;
    va_copy(v16, va);
    v17 = 4;
    v18 = v30;
    v19 = v29;
    v20 = 0;
    if ( v34 )
    {
      va_copy(v21, va1);
      v22 = 4;
      v23 = v34;
      v24 = v33;
      v25 = 0;
      v6 = (const EVENT_DESCRIPTOR *)WldpApplicationSettingQueryAudit;
      UserDataCount = 7;
    }
    else
    {
      UserDataCount = 5;
      v6 = &WldpApplicationSettingQuery;
    }
    EventWriteTransfer(RegHandle[0], v6, 0, 0, UserDataCount, &UserData);
    v9 = 0;
    return EventUnregister(RegHandle[0]);
  }
  return result;
}

```

## disassembly

```asm
0x180034164  mov     rax, rsp
0x180034167  mov     [rax+8], rbx
0x18003416b  mov     [rax+20h], r9
0x18003416f  mov     [rax+18h], r8d
0x180034173  push    rbp
0x180034174  push    rsi
0x180034175  push    rdi
0x180034176  lea     rbp, [rax-37h]
0x18003417a  sub     rsp, 0D0h
0x180034181  mov     rax, cs:__security_cookie
0x180034188  xor     rax, rsp
0x18003418b  mov     [rbp+2Fh+var_20], rax
0x18003418f  mov     rdi, rdx
0x180034192  mov     rsi, rcx
0x180034195  mov     dword ptr [rsp+30h], 0
0x18003419d  mov     [rbp+2Fh+RegHandle], 0
0x1800341a5  lea     r9, [rbp+2Fh+RegHandle]; RegHandle
0x1800341a9  xor     r8d, r8d; CallbackContext
0x1800341ac  xor     edx, edx; EnableCallback
0x1800341ae  lea     rcx, SrpEventProviderId; ProviderId
0x1800341b5  call    cs:__imp_EventRegister
0x1800341bb  test    eax, eax
0x1800341bd  jnz     loc_1800342AC
0x1800341c3  lea     rax, [rbp+2Fh+RegHandle]
0x1800341c7  mov     [rbp+2Fh+var_A0], rax
0x1800341cb  mov     ebx, 1
0x1800341d0  mov     [rbp+2Fh+var_98], bl
0x1800341d3  mov     [rsp+30h], ebx
0x1800341d7  mov     rax, [rsi+8]
0x1800341db  mov     [rbp+2Fh+var_90.Ptr], rax
0x1800341df  movzx   eax, word ptr [rsi+2]
0x1800341e3  mov     [rbp+2Fh+var_90.Size], eax
0x1800341e6  mov     dword ptr [rbp+2Fh+var_90.0Ch], 0
0x1800341ed  mov     rax, [rdi+8]
0x1800341f1  mov     [rbp+2Fh+var_80], rax
0x1800341f5  movzx   eax, word ptr [rdi+2]
0x1800341f9  mov     [rbp+2Fh+var_78], eax
0x1800341fc  mov     [rbp+2Fh+var_74], 0
0x180034203  lea     rax, [rbp+2Fh+arg_10]
0x180034207  mov     [rbp+2Fh+var_70], rax
0x18003420b  mov     [rbp+2Fh+var_68], 4
0x180034213  lea     rax, [rbp+2Fh+arg_18]
0x180034217  mov     [rbp+2Fh+var_60], rax
0x18003421b  mov     [rbp+2Fh+var_58], 4
0x180034223  mov     rax, [rbp+2Fh+arg_28]
0x180034227  mov     [rbp+2Fh+var_50], rax
0x18003422b  mov     eax, dword ptr [rbp+2Fh+arg_20]
0x18003422e  mov     [rbp+2Fh+var_48], eax
0x180034231  mov     [rbp+2Fh+var_44], 0
0x180034238  mov     rax, [rbp+2Fh+arg_40]
0x18003423c  test    rax, rax
0x18003423f  jz      short loc_18003426E
0x180034241  lea     rcx, [rbp+2Fh+arg_30]
0x180034245  mov     [rbp+2Fh+var_40], rcx
0x180034249  mov     [rbp+2Fh+var_38], 4
0x180034251  mov     [rbp+2Fh+var_30], rax
0x180034255  mov     eax, dword ptr [rbp+2Fh+arg_38]
0x180034258  mov     [rbp+2Fh+var_28], eax
0x18003425b  mov     [rbp+2Fh+var_24], 0
0x180034262  lea     rdx, WldpApplicationSettingQueryAudit
0x180034269  lea     eax, [rbx+6]
0x18003426c  jmp     short loc_18003427A
0x18003426e  mov     eax, 5
0x180034273  lea     rdx, WldpApplicationSettingQuery; EventDescriptor
0x18003427a  lea     rcx, [rbp+2Fh+var_90]
0x18003427e  mov     [rsp+0E0h+UserData], rcx; UserData
0x180034283  mov     [rsp+0E0h+UserDataCount], eax; UserDataCount
0x180034287  xor     r9d, r9d; RelatedActivityId
0x18003428a  xor     r8d, r8d; ActivityId
0x18003428d  mov     rcx, [rbp+2Fh+RegHandle]; RegHandle
0x180034291  call    cs:__imp_EventWriteTransfer
0x180034297  and     ebx, 0FFFFFFFEh
0x18003429a  mov     [rsp+30h], ebx
0x18003429e  mov     [rbp+2Fh+var_98], 0
0x1800342a2  mov     rcx, [rbp+2Fh+RegHandle]; RegHandle
0x1800342a6  call    cs:__imp_EventUnregister
0x1800342ac  mov     rcx, [rbp+2Fh+var_20]
0x1800342b0  xor     rcx, rsp; StackCookie
0x1800342b3  call    __security_check_cookie
0x1800342b8  mov     rbx, [rsp+0E0h+arg_0]
0x1800342c0  add     rsp, 0D0h
0x1800342c7  pop     rdi
0x1800342c8  pop     rsi
0x1800342c9  pop     rbp
0x1800342ca  retn
```
