# UmpoCheckAndUpdateOverlayNotification

- ea: `0x18000a990`
- end: `0x18000ab19`
- name: `UmpoCheckAndUpdateOverlayNotification`
- size: `393`
- prototype: `__int64 __fastcall(_BYTE *)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a030`
- `0x18000a680`
- `0x18000d9f0`
- `0x18000e750`

## callees

- `0x180002d8c`
- `0x18000a990`
- `0x180010070`
- `0x1800188bc`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000aac0`
- `ntdll!RtlNtStatusToDosError` at `0x18000aaef`
- `ntdll!RtlNtStatusToDosError` at `0x18000aac0`
- `ntdll!RtlNtStatusToDosError` at `0x18000aaef`
- `ntdll!NtQueryWnfStateData` at `0x18000aa0c`
- `ntdll!NtQueryWnfStateData` at `0x18000aa0c`
- `ntdll!RtlPublishWnfStateData` at `0x18000aab6`
- `ntdll!RtlPublishWnfStateData` at `0x18000aab6`

## pseudocode

```c
__int64 __fastcall UmpoCheckAndUpdateOverlayNotification(_BYTE *a1)
{
  NTSTATUS v2; // eax
  ULONG ActualOverlayScheme; // ebx
  UUID v4; // xmm6
  char v5; // al
  char v6; // si
  NTSTATUS v7; // esi
  int v9; // [rsp+38h] [rbp-49h] BYREF
  unsigned int v10[3]; // [rsp+3Ch] [rbp-45h] BYREF
  UUID Buf2; // [rsp+48h] [rbp-39h] BYREF
  UUID Buf1; // [rsp+58h] [rbp-29h] BYREF
  UUID v13; // [rsp+68h] [rbp-19h] BYREF
  int v14; // [rsp+78h] [rbp-9h]
  UUID v15; // [rsp+80h] [rbp-1h] BYREF
  int v16; // [rsp+90h] [rbp+Fh]

  v9 = 0;
  v10[0] = 20;
  v16 = 0;
  v14 = 0;
  Buf1 = 0;
  Buf2 = 0;
  v15 = 0;
  v13 = 0;
  if ( a1 )
    *a1 = 0;
  v2 = NtQueryWnfStateData(&WNF_PO_OVERLAY_POWER_SCHEME_UPDATE, 0, 0, &v9, &v15, v10);
  if ( v2 < 0 || v9 && v10[0] < 0x14 )
  {
    return RtlNtStatusToDosError(v2);
  }
  else
  {
    ActualOverlayScheme = UmpoGetActualOverlayScheme(&Buf1);
    if ( !ActualOverlayScheme )
    {
      v4 = Buf1;
      if ( v9 )
      {
        v5 = v16 & 1;
        Buf2 = v15;
      }
      else
      {
        v5 = 0;
        Buf2 = Buf1;
      }
      v6 = UmpoOnAcPower;
      if ( !v9 || v5 != UmpoOnAcPower || memcmp_0(&Buf1, &Buf2, 0x10u) )
      {
        v13 = v4;
        if ( v6 )
          v14 |= 1u;
        v7 = RtlPublishWnfStateData(WNF_PO_OVERLAY_POWER_SCHEME_UPDATE, 0, &v13, 20, 0);
        ActualOverlayScheme = RtlNtStatusToDosError(v7);
        if ( a1 && v7 >= 0 && memcmp_0(&Buf1, &Buf2, 0x10u) )
          *a1 = 1;
      }
    }
  }
  return ActualOverlayScheme;
}

```

## disassembly

```asm
0x18000a990  mov     rax, rsp
0x18000a993  push    rbp
0x18000a994  push    rbx
0x18000a995  push    rsi
0x18000a996  push    rdi
0x18000a997  lea     rbp, [rax-5Fh]
0x18000a99b  sub     rsp, 0B8h
0x18000a9a2  movaps  xmmword ptr [rax-38h], xmm6
0x18000a9a6  mov     rax, cs:__security_cookie
0x18000a9ad  xor     rax, rsp
0x18000a9b0  mov     [rbp+57h+var_40], rax
0x18000a9b4  xor     eax, eax
0x18000a9b6  mov     [rbp+57h+var_A0], 0
0x18000a9bd  mov     [rbp+57h+var_9C], 14h
0x18000a9c4  xorps   xmm0, xmm0
0x18000a9c7  mov     [rbp+57h+var_48], eax
0x18000a9ca  xorps   xmm1, xmm1
0x18000a9cd  mov     [rbp+57h+var_60], eax
0x18000a9d0  mov     rdi, rcx
0x18000a9d3  movups  [rbp+57h+Buf1], xmm0
0x18000a9d7  movups  [rbp+57h+Buf2], xmm1
0x18000a9db  movups  [rbp+57h+var_58], xmm0
0x18000a9df  movups  [rbp+57h+var_70], xmm1
0x18000a9e3  test    rcx, rcx
0x18000a9e6  jz      short loc_18000A9EA
0x18000a9e8  mov     [rcx], al
0x18000a9ea  lea     rax, [rbp+57h+var_9C]
0x18000a9ee  xor     r8d, r8d
0x18000a9f1  mov     [rsp+28h], rax
0x18000a9f6  lea     r9, [rbp+57h+var_A0]
0x18000a9fa  lea     rax, [rbp+57h+var_58]
0x18000a9fe  xor     edx, edx
0x18000aa00  lea     rcx, WNF_PO_OVERLAY_POWER_SCHEME_UPDATE
0x18000aa07  mov     [rsp+0D0h+var_B0], rax
0x18000aa0c  call    cs:__imp_NtQueryWnfStateData
0x18000aa12  test    eax, eax
0x18000aa14  js      loc_18000AAED
0x18000aa1a  cmp     [rbp+57h+var_A0], 0
0x18000aa1e  jz      short loc_18000AA2A
0x18000aa20  cmp     [rbp+57h+var_9C], 14h
0x18000aa24  jb      loc_18000AAED
0x18000aa2a  mov     dl, cs:UmpoOnAcPower
0x18000aa30  lea     rcx, [rbp+57h+Buf1]; Uuid
0x18000aa34  call    UmpoGetActualOverlayScheme
0x18000aa39  mov     ebx, eax
0x18000aa3b  test    eax, eax
0x18000aa3d  jnz     loc_18000AAF7
0x18000aa43  mov     ecx, [rbp+57h+var_A0]
0x18000aa46  movaps  xmm6, [rbp+57h+Buf1]
0x18000aa4a  test    ecx, ecx
0x18000aa4c  jz      short loc_18000AA5E
0x18000aa4e  movups  xmm0, [rbp+57h+var_58]
0x18000aa52  mov     al, byte ptr [rbp+57h+var_48]
0x18000aa55  and     al, 1
0x18000aa57  movdqu  [rbp+57h+Buf2], xmm0
0x18000aa5c  jmp     short loc_18000AA65
0x18000aa5e  xor     al, al
0x18000aa60  movdqa  [rbp+57h+Buf2], xmm6
0x18000aa65  mov     sil, cs:UmpoOnAcPower
0x18000aa6c  test    ecx, ecx
0x18000aa6e  jz      short loc_18000AA8C
0x18000aa70  cmp     al, sil
0x18000aa73  jnz     short loc_18000AA8C
0x18000aa75  mov     r8d, 10h; Size
0x18000aa7b  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18000aa7f  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18000aa83  call    memcmp_0
0x18000aa88  test    eax, eax
0x18000aa8a  jz      short loc_18000AAF7
0x18000aa8c  movdqu  [rbp+57h+var_70], xmm6
0x18000aa91  test    sil, sil
0x18000aa94  jz      short loc_18000AA9A
0x18000aa96  or      [rbp+57h+var_60], 1
0x18000aa9a  mov     rcx, cs:WNF_PO_OVERLAY_POWER_SCHEME_UPDATE
0x18000aaa1  lea     r8, [rbp+57h+var_70]
0x18000aaa5  mov     r9d, 14h
0x18000aaab  mov     [rsp+0D0h+var_B0], 0
0x18000aab4  xor     edx, edx
0x18000aab6  call    cs:__imp_RtlPublishWnfStateData
0x18000aabc  mov     ecx, eax; Status
0x18000aabe  mov     esi, eax
0x18000aac0  call    cs:__imp_RtlNtStatusToDosError
0x18000aac6  mov     ebx, eax
0x18000aac8  test    rdi, rdi
0x18000aacb  jz      short loc_18000AAF7
0x18000aacd  test    esi, esi
0x18000aacf  js      short loc_18000AAF7
0x18000aad1  mov     r8d, 10h; Size
0x18000aad7  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18000aadb  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18000aadf  call    memcmp_0
0x18000aae4  test    eax, eax
0x18000aae6  jz      short loc_18000AAF7
0x18000aae8  mov     byte ptr [rdi], 1
0x18000aaeb  jmp     short loc_18000AAF7
0x18000aaed  mov     ecx, eax; Status
0x18000aaef  call    cs:__imp_RtlNtStatusToDosError
0x18000aaf5  mov     ebx, eax
0x18000aaf7  mov     eax, ebx
0x18000aaf9  mov     rcx, [rbp+57h+var_40]
0x18000aafd  xor     rcx, rsp; StackCookie
0x18000ab00  call    __security_check_cookie
0x18000ab05  movaps  xmm6, [rsp+0D0h+var_38+8]
0x18000ab0d  add     rsp, 0B8h
0x18000ab14  pop     rdi
0x18000ab15  pop     rsi
0x18000ab16  pop     rbx
0x18000ab17  pop     rbp
0x18000ab18  retn
```
