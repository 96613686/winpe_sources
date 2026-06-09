# WindowsKeyCreation_SubThread(void *)

- ea: `0x14002f4a0`
- end: `0x14002f5f0`
- name: `?WindowsKeyCreation_SubThread@@YAXPEAX@Z`
- size: `336`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400078b8`
- `0x140009278`
- `0x14002d050`
- `0x14002d8b4`
- `0x14002f4a0`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x14002f5d4`
- `ntoskrnl!PsTerminateSystemThread` at `0x14002f5d4`

## pseudocode

```c
void __fastcall WindowsKeyCreation_SubThread(_QWORD *a1)
{
  NTSTATUS WindowsSrk; // ebx
  __int64 v3; // rdi
  int v4; // r14d
  struct TpmStack *v5; // r15
  int v6; // esi
  int WindowsEk; // eax

  if ( !a1 || (v3 = a1[1]) == 0 )
  {
LABEL_2:
    WindowsSrk = -1073741811;
    goto LABEL_21;
  }
  if ( *(_DWORD *)v3 < 3u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids);
    goto LABEL_2;
  }
  v4 = *(_DWORD *)(v3 + 24);
  WindowsSrk = 0;
  v5 = *(struct TpmStack **)(v3 + 8);
  v6 = 0;
  if ( (v4 & 2) != 0 )
  {
    WindowsSrk = CreateWindowsSrk(
                   *(struct Tpm20Context **)(v3 + 16),
                   *(struct TpmStack **)(v3 + 8),
                   (struct Event *)(a1 + 3));
    if ( WindowsSrk < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        37,
        WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids,
        (unsigned int)WindowsSrk);
    }
  }
  if ( (v4 & 8) != 0 )
  {
    WindowsEk = CreateWindowsEk(*(struct Tpm20Context **)(v3 + 16), v5, (struct Event *)(a1 + 3));
    v6 = WindowsEk;
    if ( WindowsEk < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        38,
        WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids,
        (unsigned int)WindowsEk);
    }
  }
  if ( WindowsSrk >= 0 )
  {
    if ( v6 >= 0 )
    {
      WindowsSrk = 0;
      goto LABEL_25;
    }
    WindowsSrk = v6;
  }
LABEL_21:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      39,
      WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids,
      (unsigned int)WindowsSrk);
LABEL_25:
  PsTerminateSystemThread(WindowsSrk);
}

```

## disassembly

```asm
0x14002f4a0  push    rbx
0x14002f4a2  push    rbp
0x14002f4a3  push    rsi
0x14002f4a4  push    rdi
0x14002f4a5  push    r12
0x14002f4a7  push    r14
0x14002f4a9  push    r15
0x14002f4ab  sub     rsp, 20h
0x14002f4af  lea     r12, WPP_GLOBAL_Control
0x14002f4b6  mov     rbp, rcx
0x14002f4b9  test    rcx, rcx
0x14002f4bc  jnz     short loc_14002F4C8
0x14002f4be  mov     ebx, 0C000000Dh
0x14002f4c3  jmp     loc_14002F5A3
0x14002f4c8  mov     rdi, [rcx+8]
0x14002f4cc  test    rdi, rdi
0x14002f4cf  jz      short loc_14002F4BE
0x14002f4d1  cmp     dword ptr [rdi], 3
0x14002f4d4  jnb     short loc_14002F500
0x14002f4d6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f4dd  cmp     rcx, r12
0x14002f4e0  jz      short loc_14002F4BE
0x14002f4e2  mov     eax, [rcx+2Ch]
0x14002f4e5  test    al, 1
0x14002f4e7  jz      short loc_14002F4BE
0x14002f4e9  mov     rcx, [rcx+18h]
0x14002f4ed  lea     r8, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002f4f4  mov     edx, 24h ; '$'
0x14002f4f9  call    WPP_SF_
0x14002f4fe  jmp     short loc_14002F4BE
0x14002f500  mov     r14d, [rdi+18h]
0x14002f504  xor     ebx, ebx
0x14002f506  mov     r15, [rdi+8]
0x14002f50a  xor     esi, esi
0x14002f50c  test    r14b, 2
0x14002f510  jz      short loc_14002F551
0x14002f512  lea     r8, [rcx+18h]; struct Event *
0x14002f516  mov     rdx, r15; struct TpmStack *
0x14002f519  mov     rcx, [rdi+10h]; struct Tpm20Context *
0x14002f51d  call    ?CreateWindowsSrk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVEvent@@@Z; CreateWindowsSrk(Tpm20Context *,TpmStack *,Event *)
0x14002f522  mov     ebx, eax
0x14002f524  test    eax, eax
0x14002f526  jns     short loc_14002F551
0x14002f528  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f52f  cmp     rcx, r12
0x14002f532  jz      short loc_14002F551
0x14002f534  mov     eax, [rcx+2Ch]
0x14002f537  test    al, 1
0x14002f539  jz      short loc_14002F551
0x14002f53b  mov     rcx, [rcx+18h]
0x14002f53f  lea     edx, [rsi+25h]
0x14002f542  mov     r9d, ebx
0x14002f545  lea     r8, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002f54c  call    WPP_SF_d
0x14002f551  test    r14b, 8
0x14002f555  jz      short loc_14002F599
0x14002f557  mov     rcx, [rdi+10h]; struct Tpm20Context *
0x14002f55b  lea     r8, [rbp+18h]; struct Event *
0x14002f55f  mov     rdx, r15; struct TpmStack *
0x14002f562  call    ?CreateWindowsEk@@YAJPEAVTpm20Context@@PEAVTpmStack@@PEAVEvent@@@Z; CreateWindowsEk(Tpm20Context *,TpmStack *,Event *)
0x14002f567  mov     esi, eax
0x14002f569  test    eax, eax
0x14002f56b  jns     short loc_14002F599
0x14002f56d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f574  cmp     rcx, r12
0x14002f577  jz      short loc_14002F599
0x14002f579  mov     edx, [rcx+2Ch]
0x14002f57c  test    dl, 1
0x14002f57f  jz      short loc_14002F599
0x14002f581  mov     rcx, [rcx+18h]
0x14002f585  lea     r8, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002f58c  mov     edx, 26h ; '&'
0x14002f591  mov     r9d, eax
0x14002f594  call    WPP_SF_d
0x14002f599  test    ebx, ebx
0x14002f59b  js      short loc_14002F5A3
0x14002f59d  test    esi, esi
0x14002f59f  jns     short loc_14002F5D0
0x14002f5a1  mov     ebx, esi
0x14002f5a3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f5aa  cmp     rcx, r12
0x14002f5ad  jz      short loc_14002F5D2
0x14002f5af  mov     eax, [rcx+2Ch]
0x14002f5b2  test    al, 2
0x14002f5b4  jz      short loc_14002F5D2
0x14002f5b6  mov     rcx, [rcx+18h]
0x14002f5ba  lea     r8, WPP_32c877de7c423443f3d1f1d1359134d8_Traceguids
0x14002f5c1  mov     edx, 27h ; '''
0x14002f5c6  mov     r9d, ebx
0x14002f5c9  call    WPP_SF_d
0x14002f5ce  jmp     short loc_14002F5D2
0x14002f5d0  xor     ebx, ebx
0x14002f5d2  mov     ecx, ebx; ExitStatus
0x14002f5d4  call    cs:__imp_PsTerminateSystemThread
0x14002f5db  nop     dword ptr [rax+rax+00h]
0x14002f5e0  add     rsp, 20h
0x14002f5e4  pop     r15
0x14002f5e6  pop     r14
0x14002f5e8  pop     r12
0x14002f5ea  pop     rdi
0x14002f5eb  pop     rsi
0x14002f5ec  pop     rbp
0x14002f5ed  pop     rbx
0x14002f5ee  retn
```
