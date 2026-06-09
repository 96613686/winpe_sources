# CWlanProfileStore::InitializeWlan(void)

- ea: `0x18002af7c`
- end: `0x18002b066`
- name: `?InitializeWlan@CWlanProfileStore@@IEAAXXZ`
- size: `234`
- prototype: `void __fastcall(PVOID pCallbackContext)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180029a08`
- `0x18002b860`

## callees

- `0x18002a2ec`
- `0x18002af7c`
- `0x18002b5dc`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x18002affb`
- `wlanapi!WlanCloseHandle` at `0x18002affb`
- `wlanapi!WlanOpenHandle` at `0x18002afb6`
- `wlanapi!WlanOpenHandle` at `0x18002afb6`
- `wlanapi!WlanRegisterNotification` at `0x18002b03c`
- `wlanapi!WlanRegisterNotification` at `0x18002b03c`

## pseudocode

```c
void __fastcall CWlanProfileStore::InitializeWlan(HANDLE *pCallbackContext)
{
  HANDLE *v2; // rdi
  signed int v3; // eax
  __int64 pdwPrevNotifSource; // [rsp+60h] [rbp+8h] BYREF
  signed int v5; // [rsp+68h] [rbp+10h]
  DWORD pdwNegotiatedVersion; // [rsp+70h] [rbp+18h] BYREF
  char *v7; // [rsp+78h] [rbp+20h]

  pdwPrevNotifSource = (__int64)pCallbackContext;
  v2 = pCallbackContext + 29;
  v7 = (char *)(pCallbackContext + 29);
  if ( pCallbackContext[29] )
  {
LABEL_10:
    LODWORD(pdwPrevNotifSource) = 0;
    WlanRegisterNotification(*v2, 8u, 1, WlanNotify, pCallbackContext, 0, (PDWORD)&pdwPrevNotifSource);
    pdwPrevNotifSource = 0xD00000008LL;
    CWlanProfileStore::NotifyListeners(
      (CWlanProfileStore *)pCallbackContext,
      (const struct CWlanNotification *)&pdwPrevNotifSource);
    return;
  }
  CWlanProfileStore::ClearProfileLists((CWlanProfileStore *)pCallbackContext);
  pdwNegotiatedVersion = 0;
  v3 = WlanOpenHandle(1u, 0, &pdwNegotiatedVersion, v2);
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  v5 = v3;
  if ( v3 < 0 )
    goto LABEL_5;
  if ( pdwNegotiatedVersion )
  {
    if ( !*v2 )
      return;
    goto LABEL_10;
  }
  if ( *v2 )
  {
    WlanCloseHandle(*v2, 0);
LABEL_5:
    *v2 = 0;
  }
}

```

## disassembly

```asm
0x18002af7c  mov     [rsp+arg_0], rcx
0x18002af81  push    rsi
0x18002af82  push    rdi
0x18002af83  sub     rsp, 48h
0x18002af87  mov     rsi, rcx
0x18002af8a  lea     rdi, [rcx+0E8h]
0x18002af91  mov     [rsp+58h+arg_18], rdi
0x18002af96  cmp     qword ptr [rdi], 0
0x18002af9a  jnz     short loc_18002B009
0x18002af9c  call    ?ClearProfileLists@CWlanProfileStore@@IEAAXXZ; CWlanProfileStore::ClearProfileLists(void)
0x18002afa1  mov     [rsp+58h+pdwNegotiatedVersion], 0
0x18002afa9  mov     r9, rdi; phClientHandle
0x18002afac  lea     r8, [rsp+58h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18002afb1  xor     edx, edx; pReserved
0x18002afb3  lea     ecx, [rdx+1]; dwClientVersion
0x18002afb6  call    cs:__imp_WlanOpenHandle
0x18002afbc  test    eax, eax
0x18002afbe  jle     short loc_18002AFC8
0x18002afc0  movzx   eax, ax
0x18002afc3  or      eax, 80070000h
0x18002afc8  mov     [rsp+58h+arg_8], eax
0x18002afcc  jmp     short loc_18002AFDC
0x18002afce  mov     rsi, [rsp+58h+arg_0]
0x18002afd3  mov     eax, [rsp+58h+arg_8]
0x18002afd7  mov     rdi, [rsp+58h+arg_18]
0x18002afdc  test    eax, eax
0x18002afde  jns     short loc_18002AFE9
0x18002afe0  mov     qword ptr [rdi], 0
0x18002afe7  jmp     short loc_18002B05F
0x18002afe9  cmp     [rsp+58h+pdwNegotiatedVersion], 1
0x18002afee  jnb     short loc_18002B003
0x18002aff0  cmp     qword ptr [rdi], 0
0x18002aff4  jz      short loc_18002B05F
0x18002aff6  xor     edx, edx; pReserved
0x18002aff8  mov     rcx, [rdi]; hClientHandle
0x18002affb  call    cs:__imp_WlanCloseHandle
0x18002b001  jmp     short loc_18002AFE0
0x18002b003  cmp     qword ptr [rdi], 0
0x18002b007  jz      short loc_18002B05F
0x18002b009  mov     dword ptr [rsp+58h+arg_0], 0
0x18002b011  lea     rax, [rsp+58h+arg_0]
0x18002b016  mov     [rsp+58h+pdwPrevNotifSource], rax; pdwPrevNotifSource
0x18002b01b  mov     [rsp+58h+pReserved], 0; pReserved
0x18002b024  mov     [rsp+58h+pCallbackContext], rsi; pCallbackContext
0x18002b029  lea     r9, ?WlanNotify@@YAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; funcCallback
0x18002b030  mov     edx, 8; dwNotifSource
0x18002b035  lea     r8d, [rdx-7]; bIgnoreDuplicate
0x18002b039  mov     rcx, [rdi]; hClientHandle
0x18002b03c  call    cs:__imp_WlanRegisterNotification
0x18002b042  mov     dword ptr [rsp+58h+arg_0], 8
0x18002b04a  mov     dword ptr [rsp+58h+arg_0+4], 0Dh
0x18002b052  lea     rdx, [rsp+58h+arg_0]; struct CWlanNotification *
0x18002b057  mov     rcx, rsi; this
0x18002b05a  call    ?NotifyListeners@CWlanProfileStore@@QEAAXAEBVCWlanNotification@@@Z; CWlanProfileStore::NotifyListeners(CWlanNotification const &)
0x18002b05f  add     rsp, 48h
0x18002b063  pop     rdi
0x18002b064  pop     rsi
0x18002b065  retn
```
