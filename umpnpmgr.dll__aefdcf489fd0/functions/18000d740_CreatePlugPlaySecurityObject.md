# CreatePlugPlaySecurityObject

- ea: `0x18000d740`
- end: `0x18000d9d5`
- name: `CreatePlugPlaySecurityObject`
- size: `661`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000cf30`

## callees

- `0x18000d740`
- `0x180018970`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000d99d`
- `ntdll!RtlNtStatusToDosError` at `0x18000d99d`
- `ntdll!NtSetInformationThread` at `0x18000d990`
- `ntdll!NtSetInformationThread` at `0x18000d990`
- `ntdll!NtClose` at `0x18000d96e`
- `ntdll!NtClose` at `0x18000d96e`
- `ntdll!RtlNewSecurityObject` at `0x18000d947`
- `ntdll!RtlNewSecurityObject` at `0x18000d947`
- `ntdll!RtlCreateAndSetSD` at `0x18000d914`
- `ntdll!RtlCreateAndSetSD` at `0x18000d914`
- `ntdll!NtOpenThreadToken` at `0x18000d8e3`
- `ntdll!NtOpenThreadToken` at `0x18000d8e3`
- `ntdll!RtlImpersonateSelf` at `0x18000d790`
- `ntdll!RtlImpersonateSelf` at `0x18000d790`
- `ntdll!RtlAdjustPrivilege` at `0x18000d785`
- `ntdll!RtlAdjustPrivilege` at `0x18000d7b1`
- `ntdll!RtlAdjustPrivilege` at `0x18000d785`
- `ntdll!RtlAdjustPrivilege` at `0x18000d7b1`
- `ntdll!RtlFreeHeap` at `0x18000d963`
- `ntdll!RtlFreeHeap` at `0x18000d963`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d9a7`

## pseudocode

```c
_BOOL8 CreatePlugPlaySecurityObject()
{
  int v0; // ebx
  NTSTATUS v1; // eax
  DWORD v2; // ebx
  unsigned __int8 OldValue[8]; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v7; // [rsp+50h] [rbp-B0h]
  __int128 v8; // [rsp+60h] [rbp-A0h]
  __int128 v9; // [rsp+70h] [rbp-90h]
  __int128 v10; // [rsp+80h] [rbp-80h]
  __int128 v11; // [rsp+90h] [rbp-70h]
  __int128 v12; // [rsp+A0h] [rbp-60h]
  char v13; // [rsp+B3h] [rbp-4Dh]
  char v14; // [rsp+C3h] [rbp-3Dh]
  _OWORD AceData[6]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v16; // [rsp+130h] [rbp+30h]
  char v17; // [rsp+132h] [rbp+32h]
  char v18; // [rsp+133h] [rbp+33h]
  int v19; // [rsp+134h] [rbp+34h]
  __int64 v20; // [rsp+138h] [rbp+38h]
  __int16 v21; // [rsp+140h] [rbp+40h]
  char v22; // [rsp+142h] [rbp+42h]
  char v23; // [rsp+143h] [rbp+43h]
  int v24; // [rsp+144h] [rbp+44h]
  __int64 v25; // [rsp+148h] [rbp+48h]

  OldValue[0] = 0;
  CreatorDescriptor = 0;
  TokenHandle = 0;
  RtlAdjustPrivilege(0x15u, 1u, 0, OldValue);
  v0 = RtlImpersonateSelf(SecurityImpersonation);
  if ( v0 >= 0 )
  {
    v0 = RtlAdjustPrivilege(8u, 1u, 1u, OldValue);
    if ( v0 >= 0 )
    {
      LOWORD(v7) = 0;
      BYTE2(v7) = 0;
      DWORD1(v7) = -536870912;
      LOWORD(v8) = 1;
      *((_QWORD *)&v7 + 1) = PnpSvchostGlobalData + 80;
      *((_QWORD *)&v8 + 1) = PnpSvchostGlobalData + 24;
      *((_QWORD *)&v9 + 1) = PnpSvchostGlobalData + 32;
      *((_QWORD *)&v10 + 1) = PnpSvchostGlobalData + 88;
      *((_QWORD *)&v11 + 1) = PnpSvchostGlobalData + 40;
      *((_QWORD *)&v12 + 1) = PnpSvchostGlobalData + 48;
      AceData[0] = v7;
      v18 = v13;
      v20 = PnpSvchostGlobalData + 8;
      v25 = PnpSvchostGlobalData + 8;
      BYTE2(v8) = 0;
      DWORD1(v8) = 0x10000000;
      AceData[1] = v8;
      LOWORD(v9) = 0;
      BYTE2(v9) = 0;
      DWORD1(v9) = 0x10000000;
      AceData[2] = v9;
      LOWORD(v10) = 0;
      BYTE2(v10) = 0;
      DWORD1(v10) = -1610612736;
      AceData[3] = v10;
      LOWORD(v11) = 0;
      BYTE2(v11) = 0;
      DWORD1(v11) = 64;
      LOWORD(v12) = 0;
      BYTE2(v12) = 0;
      DWORD1(v12) = 64;
      v23 = v14;
      AceData[4] = v11;
      AceData[5] = v12;
      v16 = 2;
      v17 = -64;
      v19 = 2;
      v21 = 2;
      v22 = 0x80;
      v24 = 0x10000000;
      v0 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
      if ( v0 >= 0 )
      {
        v0 = RtlCreateAndSetSD(
               AceData,
               8u,
               *(PSID *)(PnpSvchostGlobalData + 32),
               *(PSID *)(PnpSvchostGlobalData + 32),
               &CreatorDescriptor);
        if ( v0 >= 0 )
        {
          v0 = RtlNewSecurityObject(
                 0,
                 CreatorDescriptor,
                 &PlugPlaySecurityObject,
                 0,
                 TokenHandle,
                 &PlugPlaySecurityObjectMapping);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, CreatorDescriptor);
        }
        NtClose(TokenHandle);
      }
    }
    TokenHandle = 0;
    v1 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
    if ( v1 < 0 )
      v0 = v1;
  }
  v2 = RtlNtStatusToDosError(v0);
  SetLastError(v2);
  return v2 == 0;
}

```

## disassembly

```asm
0x18000d740  mov     [rsp-8+arg_0], rbx
0x18000d745  mov     [rsp-8+arg_8], rdi
0x18000d74a  push    rbp
0x18000d74b  lea     rbp, [rsp-60h]
0x18000d750  sub     rsp, 160h
0x18000d757  mov     rax, cs:__security_cookie
0x18000d75e  xor     rax, rsp
0x18000d761  mov     [rbp+60h+var_10], rax
0x18000d765  xor     edi, edi
0x18000d767  mov     [rsp+160h+OldValue], 0
0x18000d76c  lea     r9, [rsp+160h+OldValue]; OldValue
0x18000d771  mov     [rsp+160h+CreatorDescriptor], rdi
0x18000d776  xor     r8d, r8d; ForThread
0x18000d779  mov     [rsp+160h+TokenHandle], rdi
0x18000d77e  mov     dl, 1; NewValue
0x18000d780  mov     ecx, 15h; Privilege
0x18000d785  call    cs:__imp_RtlAdjustPrivilege
0x18000d78b  mov     ecx, 2; ImpersonationLevel
0x18000d790  call    cs:__imp_RtlImpersonateSelf
0x18000d796  mov     ebx, eax
0x18000d798  test    eax, eax
0x18000d79a  js      loc_18000D99B
0x18000d7a0  mov     r8b, 1; ForThread
0x18000d7a3  lea     r9, [rsp+160h+OldValue]; OldValue
0x18000d7a8  movzx   edx, r8b; NewValue
0x18000d7ac  mov     ecx, 8; Privilege
0x18000d7b1  call    cs:__imp_RtlAdjustPrivilege
0x18000d7b7  mov     ebx, eax
0x18000d7b9  test    eax, eax
0x18000d7bb  js      loc_18000D974
0x18000d7c1  mov     rcx, cs:PnpSvchostGlobalData
0x18000d7c8  lea     r9, [rsp+160h+TokenHandle]; TokenHandle
0x18000d7cd  mov     word ptr [rsp+160h+var_110], di
0x18000d7d2  xor     r8d, r8d; OpenAsSelf
0x18000d7d5  mov     byte ptr [rsp+160h+var_110+2], dil
0x18000d7da  mov     edx, 8; DesiredAccess
0x18000d7df  mov     dword ptr [rsp+160h+var_110+4], 0E0000000h
0x18000d7e7  lea     rax, [rcx+50h]
0x18000d7eb  mov     word ptr [rsp+160h+var_100], 1
0x18000d7f2  mov     qword ptr [rsp+160h+var_110+8], rax
0x18000d7f7  lea     rax, [rcx+18h]
0x18000d7fb  movaps  xmm0, [rsp+160h+var_110]
0x18000d800  mov     qword ptr [rsp+160h+var_100+8], rax
0x18000d805  lea     rax, [rcx+20h]
0x18000d809  mov     qword ptr [rsp+160h+var_F0+8], rax
0x18000d80e  lea     rax, [rcx+58h]
0x18000d812  mov     qword ptr [rbp+60h+var_E0+8], rax
0x18000d816  lea     rax, [rcx+28h]
0x18000d81a  mov     qword ptr [rbp+60h+var_D0+8], rax
0x18000d81e  lea     rax, [rcx+30h]
0x18000d822  mov     qword ptr [rbp+60h+var_C0+8], rax
0x18000d826  add     rcx, 8
0x18000d82a  movzx   eax, [rbp+60h+var_AD]
0x18000d82e  movaps  [rbp+60h+AceData], xmm0
0x18000d832  mov     [rbp+60h+var_2D], al
0x18000d835  movzx   eax, [rbp+60h+var_9D]
0x18000d839  mov     [rbp+60h+var_28], rcx
0x18000d83d  mov     [rbp+60h+var_18], rcx
0x18000d841  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000d848  mov     byte ptr [rsp+160h+var_100+2], dil
0x18000d84d  mov     dword ptr [rsp+160h+var_100+4], 10000000h
0x18000d855  movaps  xmm1, [rsp+160h+var_100]
0x18000d85a  movaps  [rbp+60h+var_80], xmm1
0x18000d85e  mov     word ptr [rsp+160h+var_F0], di
0x18000d863  mov     byte ptr [rsp+160h+var_F0+2], dil
0x18000d868  mov     dword ptr [rsp+160h+var_F0+4], 10000000h
0x18000d870  movaps  xmm0, [rsp+160h+var_F0]
0x18000d875  movaps  [rbp+60h+var_70], xmm0
0x18000d879  mov     word ptr [rbp+60h+var_E0], di
0x18000d87d  mov     byte ptr [rbp+60h+var_E0+2], dil
0x18000d881  mov     dword ptr [rbp+60h+var_E0+4], 0A0000000h
0x18000d888  movaps  xmm1, [rbp+60h+var_E0]
0x18000d88c  movaps  [rbp+60h+var_60], xmm1
0x18000d890  mov     word ptr [rbp+60h+var_D0], di
0x18000d894  mov     byte ptr [rbp+60h+var_D0+2], dil
0x18000d898  mov     dword ptr [rbp+60h+var_D0+4], 40h ; '@'
0x18000d89f  movaps  xmm0, [rbp+60h+var_D0]
0x18000d8a3  mov     word ptr [rbp+60h+var_C0], di
0x18000d8a7  mov     byte ptr [rbp+60h+var_C0+2], dil
0x18000d8ab  mov     dword ptr [rbp+60h+var_C0+4], 40h ; '@'
0x18000d8b2  movaps  xmm1, [rbp+60h+var_C0]
0x18000d8b6  mov     [rbp+60h+var_1D], al
0x18000d8b9  movaps  [rbp+60h+var_50], xmm0
0x18000d8bd  movaps  [rbp+60h+var_40], xmm1
0x18000d8c1  mov     [rbp+60h+var_30], 2
0x18000d8c7  mov     [rbp+60h+var_2E], 0C0h
0x18000d8cb  mov     [rbp+60h+var_2C], 2
0x18000d8d2  mov     [rbp+60h+var_20], 2
0x18000d8d8  mov     [rbp+60h+var_1E], 80h
0x18000d8dc  mov     [rbp+60h+var_1C], 10000000h
0x18000d8e3  call    cs:__imp_NtOpenThreadToken
0x18000d8e9  mov     ebx, eax
0x18000d8eb  test    eax, eax
0x18000d8ed  js      loc_18000D974
0x18000d8f3  mov     rax, cs:PnpSvchostGlobalData
0x18000d8fa  lea     rcx, [rbp+60h+AceData]; AceData
0x18000d8fe  mov     edx, 8; AceCount
0x18000d903  mov     r8, [rax+20h]; OwnerSid
0x18000d907  lea     rax, [rsp+160h+CreatorDescriptor]
0x18000d90c  mov     r9, r8; GroupSid
0x18000d90f  mov     [rsp+160h+NewDescriptor], rax; NewDescriptor
0x18000d914  call    cs:__imp_RtlCreateAndSetSD
0x18000d91a  mov     ebx, eax
0x18000d91c  test    eax, eax
0x18000d91e  js      short loc_18000D969
0x18000d920  mov     rdx, [rsp+160h+CreatorDescriptor]; CreatorDescriptor
0x18000d925  lea     rax, PlugPlaySecurityObjectMapping
0x18000d92c  mov     [rsp+160h+GenericMapping], rax; GenericMapping
0x18000d931  lea     r8, PlugPlaySecurityObject; NewDescriptor
0x18000d938  mov     rax, [rsp+160h+TokenHandle]
0x18000d93d  xor     r9d, r9d; IsDirectoryObject
0x18000d940  xor     ecx, ecx; ParentDescriptor
0x18000d942  mov     [rsp+160h+NewDescriptor], rax; Token
0x18000d947  call    cs:__imp_RtlNewSecurityObject
0x18000d94d  mov     rcx, gs:60h
0x18000d956  xor     edx, edx; Flags
0x18000d958  mov     r8, [rsp+160h+CreatorDescriptor]; P
0x18000d95d  mov     ebx, eax
0x18000d95f  mov     rcx, [rcx+30h]; HeapHandle
0x18000d963  call    cs:__imp_RtlFreeHeap
0x18000d969  mov     rcx, [rsp+160h+TokenHandle]; Handle
0x18000d96e  call    cs:__imp_NtClose
0x18000d974  mov     r9d, 8; ThreadInformationLength
0x18000d97a  mov     [rsp+160h+TokenHandle], rdi
0x18000d97f  lea     r8, [rsp+160h+TokenHandle]; ThreadInformation
0x18000d984  mov     edx, 5; ThreadInformationClass
0x18000d989  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000d990  call    cs:__imp_NtSetInformationThread
0x18000d996  test    eax, eax
0x18000d998  cmovs   ebx, eax
0x18000d99b  mov     ecx, ebx; Status
0x18000d99d  call    cs:__imp_RtlNtStatusToDosError
0x18000d9a3  mov     ecx, eax; dwErrCode
0x18000d9a5  mov     ebx, eax
0x18000d9a7  call    cs:__imp_SetLastError
0x18000d9ad  test    ebx, ebx
0x18000d9af  mov     eax, edi
0x18000d9b1  setz    al
0x18000d9b4  mov     rcx, [rbp+60h+var_10]
0x18000d9b8  xor     rcx, rsp; StackCookie
0x18000d9bb  call    __security_check_cookie
0x18000d9c0  lea     r11, [rsp+160h+var_s0]
0x18000d9c8  mov     rbx, [r11+10h]
0x18000d9cc  mov     rdi, [r11+18h]
0x18000d9d0  mov     rsp, r11
0x18000d9d3  pop     rbp
0x18000d9d4  retn
```
