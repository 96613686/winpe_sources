# MpFsCtlGetTrustedDevVolumeProtectionLevel

- ea: `0x14008096c`
- end: `0x140080b14`
- name: `MpFsCtlGetTrustedDevVolumeProtectionLevel`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400448f0`

## callees

- `0x1400018a4`
- `0x1400118d0`
- `0x14008096c`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140080ace`
- `ntoskrnl!ProbeForWrite` at `0x140080ace`
- `ntoskrnl!IoThreadToProcess` at `0x1400809ce`
- `ntoskrnl!IoThreadToProcess` at `0x1400809f6`
- `ntoskrnl!IoThreadToProcess` at `0x1400809ce`
- `ntoskrnl!IoThreadToProcess` at `0x1400809f6`
- `FLTMGR!FltReleaseContext` at `0x140080aad`
- `FLTMGR!FltReleaseContext` at `0x140080aad`
- `FLTMGR!FltGetInstanceContext` at `0x140080a69`
- `FLTMGR!FltGetInstanceContext` at `0x140080a69`

## pseudocode

```c
__int64 __fastcall MpFsCtlGetTrustedDevVolumeProtectionLevel(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  struct _KPROCESS *v5; // rbx
  struct _KPROCESS *v6; // rbx
  int v8; // ebx
  PFLT_CONTEXT v9; // rcx
  __int64 v10; // rax
  int *v11; // rdi
  PFLT_CONTEXT Context; // [rsp+28h] [rbp-30h] BYREF

  Context = 0;
  v4 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
  if ( *(int *)(MpData + 868) < 0
    || (v5 = *(struct _KPROCESS **)(MpData + 232), IoThreadToProcess(KeGetCurrentThread()) == v5)
    || (v6 = *(struct _KPROCESS **)(MpData + 256), IoThreadToProcess(KeGetCurrentThread()) == v6) )
  {
    if ( v4 >= 4 )
    {
      v8 = 0;
      if ( FltGetInstanceContext(*(PFLT_INSTANCE *)(a2 + 24), &Context) >= 0 )
      {
        v9 = Context;
        if ( (*((_DWORD *)Context + 20) & 0x10) != 0 )
        {
          v8 = ((*(_DWORD *)(MpData + 868) & 0x2000) != 0) + 3;
          v9 = Context;
        }
        else
        {
          v8 = 1;
        }
        FltReleaseContext(v9);
      }
      v10 = *(_QWORD *)(a1 + 16);
      v11 = *(int **)(v10 + 56);
      ProbeForWrite(v11, *(unsigned int *)(v10 + 24), 4u);
      *v11 = v8;
      *(_QWORD *)(a1 + 32) = 4;
      return 0;
    }
    else
    {
      return 3221225507LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        30,
        WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
        *(unsigned int *)(MpData + 868));
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x14008096c  mov     [rsp+arg_10], rbx
0x140080971  mov     [rsp+arg_18], rsi
0x140080976  push    rdi
0x140080977  push    r14
0x140080979  push    r15
0x14008097b  sub     rsp, 40h
0x14008097f  mov     rax, cs:__security_cookie
0x140080986  xor     rax, rsp
0x140080989  mov     [rsp+58h+var_28], rax
0x14008098e  mov     r15, rdx
0x140080991  mov     r14, rcx
0x140080994  xor     esi, esi
0x140080996  mov     [rsp+58h+Context], rsi
0x14008099b  mov     rax, [rcx+10h]
0x14008099f  mov     edi, [rax+18h]
0x1400809a2  mov     rax, cs:MpData
0x1400809a9  mov     edx, [rax+364h]
0x1400809af  test    edx, edx
0x1400809b1  js      loc_140080A4F
0x1400809b7  mov     rcx, gs:188h; Thread
0x1400809c0  mov     rax, cs:MpData
0x1400809c7  mov     rbx, [rax+0E8h]
0x1400809ce  call    cs:__imp_IoThreadToProcess
0x1400809d5  nop     dword ptr [rax+rax+00h]
0x1400809da  cmp     rax, rbx
0x1400809dd  jz      short loc_140080A4F
0x1400809df  mov     rcx, gs:188h; Thread
0x1400809e8  mov     rax, cs:MpData
0x1400809ef  mov     rbx, [rax+100h]
0x1400809f6  call    cs:__imp_IoThreadToProcess
0x1400809fd  nop     dword ptr [rax+rax+00h]
0x140080a02  cmp     rax, rbx
0x140080a05  jz      short loc_140080A4F
0x140080a07  lea     rax, WPP_GLOBAL_Control
0x140080a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140080a15  cmp     rcx, rax
0x140080a18  jz      short loc_140080A45
0x140080a1a  mov     eax, [rcx+2Ch]
0x140080a1d  lea     ebx, [rsi+1]
0x140080a20  test    bl, al
0x140080a22  jz      short loc_140080A45
0x140080a24  mov     rcx, [rcx+18h]
0x140080a28  lea     edx, [rsi+1Eh]
0x140080a2b  mov     r9, cs:MpData
0x140080a32  mov     r9d, [r9+364h]
0x140080a39  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x140080a40  call    WPP_SF_d
0x140080a45  mov     eax, 0C0000022h
0x140080a4a  jmp     loc_140080AF2
0x140080a4f  cmp     edi, 4
0x140080a52  jnb     short loc_140080A5E
0x140080a54  mov     eax, 0C0000023h
0x140080a59  jmp     loc_140080AF2
0x140080a5e  mov     ebx, esi
0x140080a60  lea     rdx, [rsp+58h+Context]; Context
0x140080a65  mov     rcx, [r15+18h]; Instance
0x140080a69  call    cs:__imp_FltGetInstanceContext
0x140080a70  nop     dword ptr [rax+rax+00h]
0x140080a75  test    eax, eax
0x140080a77  js      short loc_140080ABA
0x140080a79  mov     rcx, [rsp+58h+Context]; Context
0x140080a7e  mov     eax, [rcx+50h]
0x140080a81  test    al, 10h
0x140080a83  jz      short loc_140080AA8
0x140080a85  mov     rax, cs:MpData
0x140080a8c  mov     ecx, [rax+364h]
0x140080a92  and     ecx, 2000h
0x140080a98  neg     ecx
0x140080a9a  sbb     ebx, ebx
0x140080a9c  neg     ebx
0x140080a9e  add     ebx, 3
0x140080aa1  mov     rcx, [rsp+58h+Context]
0x140080aa6  jmp     short loc_140080AAD
0x140080aa8  mov     ebx, 1
0x140080aad  call    cs:__imp_FltReleaseContext
0x140080ab4  nop     dword ptr [rax+rax+00h]
0x140080ab9  nop
0x140080aba  mov     rax, [r14+10h]
0x140080abe  mov     rdi, [rax+38h]
0x140080ac2  mov     edx, [rax+18h]; Length
0x140080ac5  mov     r8d, 4; Alignment
0x140080acb  mov     rcx, rdi; Address
0x140080ace  call    cs:__imp_ProbeForWrite
0x140080ad5  nop     dword ptr [rax+rax+00h]
0x140080ada  mov     [rdi], ebx
0x140080adc  mov     qword ptr [r14+20h], 4
0x140080ae4  mov     [rsp+58h+var_38], esi
0x140080ae8  jmp     short loc_140080AF0
0x140080aea  mov     esi, eax
0x140080aec  mov     [rsp+58h+var_38], eax
0x140080af0  mov     eax, esi
0x140080af2  mov     rcx, [rsp+58h+var_28]
0x140080af7  xor     rcx, rsp; StackCookie
0x140080afa  call    __security_check_cookie
0x140080aff  mov     rbx, [rsp+58h+arg_10]
0x140080b04  mov     rsi, [rsp+58h+arg_18]
0x140080b09  add     rsp, 40h
0x140080b0d  pop     r15
0x140080b0f  pop     r14
0x140080b11  pop     rdi
0x140080b12  retn
```
