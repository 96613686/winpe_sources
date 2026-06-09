# CWlanPrefLUA::DeleteProfile(_GUID const *,ushort *)

- ea: `0x180015470`
- end: `0x180015506`
- name: `?DeleteProfile@CWlanPrefLUA@@UEAAJPEBU_GUID@@PEAG@Z`
- size: `150`
- prototype: `__int64 __fastcall(CWlanPrefLUA *this, const struct _GUID *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015470`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x1800154da`
- `wlanapi!WlanCloseHandle` at `0x1800154da`
- `wlanapi!WlanOpenHandle` at `0x1800154ac`
- `wlanapi!WlanOpenHandle` at `0x1800154ac`
- `wlanapi!WlanDeleteProfile` at `0x1800154c6`
- `wlanapi!WlanDeleteProfile` at `0x1800154c6`

## pseudocode

```c
__int64 __fastcall CWlanPrefLUA::DeleteProfile(CWlanPrefLUA *this, const struct _GUID *a2, unsigned __int16 *a3)
{
  signed int v5; // ebx
  DWORD v7; // [rsp+38h] [rbp+10h] BYREF
  HANDLE hClientHandle; // [rsp+48h] [rbp+20h] BYREF

  hClientHandle = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  v7 = 0;
  v5 = WlanOpenHandle(2u, 0, &v7, &hClientHandle);
  if ( !v5 )
    v5 = WlanDeleteProfile(hClientHandle, a2, a3, 0);
  if ( hClientHandle )
    WlanCloseHandle(hClientHandle, 0);
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180015470  mov     rax, rsp
0x180015473  mov     [rax+8], rbx
0x180015477  mov     [rax+18h], rsi
0x18001547b  push    rdi
0x18001547c  sub     rsp, 20h
0x180015480  mov     qword ptr [rax+20h], 0
0x180015488  mov     rdi, r8
0x18001548b  mov     rsi, rdx
0x18001548e  test    rdx, rdx
0x180015491  jz      short loc_1800154F1
0x180015493  test    r8, r8
0x180015496  jz      short loc_1800154F1
0x180015498  xor     edx, edx; pReserved
0x18001549a  mov     dword ptr [rax+10h], 0
0x1800154a1  lea     r9, [rax+20h]; phClientHandle
0x1800154a5  lea     r8, [rax+10h]; pdwNegotiatedVersion
0x1800154a9  lea     ecx, [rdx+2]; dwClientVersion
0x1800154ac  call    cs:__imp_WlanOpenHandle
0x1800154b2  mov     ebx, eax
0x1800154b4  test    eax, eax
0x1800154b6  jnz     short loc_1800154CE
0x1800154b8  mov     rcx, [rsp+28h+hClientHandle]; hClientHandle
0x1800154bd  xor     r9d, r9d; pReserved
0x1800154c0  mov     r8, rdi; strProfileName
0x1800154c3  mov     rdx, rsi; pInterfaceGuid
0x1800154c6  call    cs:__imp_WlanDeleteProfile
0x1800154cc  mov     ebx, eax
0x1800154ce  mov     rcx, [rsp+28h+hClientHandle]; hClientHandle
0x1800154d3  test    rcx, rcx
0x1800154d6  jz      short loc_1800154E0
0x1800154d8  xor     edx, edx; pReserved
0x1800154da  call    cs:__imp_WlanCloseHandle
0x1800154e0  test    ebx, ebx
0x1800154e2  jle     short loc_1800154ED
0x1800154e4  movzx   ebx, bx
0x1800154e7  or      ebx, 80070000h
0x1800154ed  mov     eax, ebx
0x1800154ef  jmp     short loc_1800154F6
0x1800154f1  mov     eax, 80070057h
0x1800154f6  mov     rbx, [rsp+28h+arg_0]
0x1800154fb  mov     rsi, [rsp+28h+arg_10]
0x180015500  add     rsp, 20h
0x180015504  pop     rdi
0x180015505  retn
```
