# CWlanPrefLUA::RenameProfile(_GUID const *,ushort *,ushort *)

- ea: `0x180015510`
- end: `0x1800155ab`
- name: `?RenameProfile@CWlanPrefLUA@@UEAAJPEBU_GUID@@PEAG1@Z`
- size: `155`
- prototype: `__int64 __fastcall(CWlanPrefLUA *this, const struct _GUID *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015510`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x180015586`
- `wlanapi!WlanCloseHandle` at `0x180015586`
- `wlanapi!WlanRenameProfile` at `0x180015572`
- `wlanapi!WlanRenameProfile` at `0x180015572`
- `wlanapi!WlanOpenHandle` at `0x18001554f`
- `wlanapi!WlanOpenHandle` at `0x18001554f`

## pseudocode

```c
__int64 __fastcall CWlanPrefLUA::RenameProfile(
        CWlanPrefLUA *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  signed int v7; // ebx
  HANDLE hClientHandle; // [rsp+30h] [rbp-38h] BYREF
  DWORD v10; // [rsp+78h] [rbp+10h] BYREF

  hClientHandle = 0;
  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  v10 = 0;
  v7 = WlanOpenHandle(2u, 0, &v10, &hClientHandle);
  if ( !v7 )
    v7 = WlanRenameProfile(hClientHandle, a2, a3, a4, 0);
  if ( hClientHandle )
    WlanCloseHandle(hClientHandle, 0);
  if ( v7 > 0 )
    return (unsigned __int16)v7 | 0x80070000;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180015510  mov     rax, rsp
0x180015513  push    rbx
0x180015514  push    rbp
0x180015515  push    rsi
0x180015516  push    rdi
0x180015517  sub     rsp, 48h
0x18001551b  mov     qword ptr [rax-38h], 0
0x180015523  mov     rdi, r9
0x180015526  mov     rsi, r8
0x180015529  mov     rbp, rdx
0x18001552c  test    rdx, rdx
0x18001552f  jz      short loc_18001559D
0x180015531  test    r8, r8
0x180015534  jz      short loc_18001559D
0x180015536  test    r9, r9
0x180015539  jz      short loc_18001559D
0x18001553b  xor     edx, edx; pReserved
0x18001553d  mov     dword ptr [rax+10h], 0
0x180015544  lea     r9, [rax-38h]; phClientHandle
0x180015548  lea     r8, [rax+10h]; pdwNegotiatedVersion
0x18001554c  lea     ecx, [rdx+2]; dwClientVersion
0x18001554f  call    cs:__imp_WlanOpenHandle
0x180015555  mov     ebx, eax
0x180015557  test    eax, eax
0x180015559  jnz     short loc_18001557A
0x18001555b  mov     rcx, [rsp+68h+hClientHandle]; hClientHandle
0x180015560  mov     r9, rdi; strNewProfileName
0x180015563  mov     r8, rsi; strOldProfileName
0x180015566  mov     [rsp+68h+pReserved], 0; pReserved
0x18001556f  mov     rdx, rbp; pInterfaceGuid
0x180015572  call    cs:__imp_WlanRenameProfile
0x180015578  mov     ebx, eax
0x18001557a  mov     rcx, [rsp+68h+hClientHandle]; hClientHandle
0x18001557f  test    rcx, rcx
0x180015582  jz      short loc_18001558C
0x180015584  xor     edx, edx; pReserved
0x180015586  call    cs:__imp_WlanCloseHandle
0x18001558c  test    ebx, ebx
0x18001558e  jle     short loc_180015599
0x180015590  movzx   ebx, bx
0x180015593  or      ebx, 80070000h
0x180015599  mov     eax, ebx
0x18001559b  jmp     short loc_1800155A2
0x18001559d  mov     eax, 80070057h
0x1800155a2  add     rsp, 48h
0x1800155a6  pop     rdi
0x1800155a7  pop     rsi
0x1800155a8  pop     rbp
0x1800155a9  pop     rbx
0x1800155aa  retn
```
