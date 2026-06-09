# VidExoVppCreate

- ea: `0x140084884`
- end: `0x140084b3c`
- name: `VidExoVppCreate`
- size: `696`
- prototype: `__int64 __fastcall(PVOID DeferredContext, unsigned int, unsigned int, __int128 *, _QWORD *, unsigned int **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x14008413c`

## callees

- `0x140021800`
- `0x140024754`
- `0x140038630`
- `0x140084884`
- `0x140084b44`
- `0x140084d08`
- `0x140084e54`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x140084979`
- `ntoskrnl!KeInitializeDpc` at `0x140084979`
- `ntoskrnl!ExAllocatePool2` at `0x1400848b1`
- `ntoskrnl!ExAllocatePool2` at `0x1400848b1`
- `winhvr!WinHvSetDispatchNotificationEvent` at `0x140084ab4`
- `winhvr!WinHvSetDispatchNotificationEvent` at `0x140084ab4`
- `winhvr!WinHvCreateVp` at `0x1400849ad`
- `winhvr!WinHvCreateVp` at `0x1400849ad`

## string_xrefs

- `0x1400848d2`: `VidExoVppCreate`
- `0x140084ad3`: `VidExoVppCreate`
- `0x140084b0d`: `VidExoVppCreate`

## pseudocode

```c
__int64 __fastcall VidExoVppCreate(
        PVOID DeferredContext,
        unsigned int a2,
        unsigned int a3,
        __int128 *a4,
        _QWORD *a5,
        unsigned int **a6)
{
  unsigned int *Pool2; // rax
  unsigned int *v10; // rdi
  int Vp; // ebx
  __int64 v12; // rcx
  __int64 v13; // r8
  _DWORD *v14; // rax
  int v16; // [rsp+20h] [rbp-68h]
  int v17; // [rsp+20h] [rbp-68h]
  __int128 v18[5]; // [rsp+30h] [rbp-58h] BYREF

  Pool2 = (unsigned int *)ExAllocatePool2(64, 416, 1917084758);
  v10 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = a2;
    memset(Pool2 + 26, 0, 0x48u);
    *((_QWORD *)v10 + 19) = v10 + 36;
    *((_QWORD *)v10 + 18) = v10 + 36;
    memset(v10 + 44, 0, 0x48u);
    *((_QWORD *)v10 + 28) = v10 + 54;
    *((_QWORD *)v10 + 27) = v10 + 54;
    memset(v10 + 62, 0, 0x48u);
    *((_QWORD *)v10 + 37) = v10 + 72;
    *((_QWORD *)v10 + 36) = v10 + 72;
    memset(v10 + 82, 0, 0x48u);
    *((_QWORD *)v10 + 47) = v10 + 92;
    *((_QWORD *)v10 + 46) = v10 + 92;
    KeInitializeDpc((PRKDPC)(v10 + 2), VidExoVppInterceptDpcRoutine, DeferredContext);
    v12 = *((_QWORD *)DeferredContext + 81);
    v18[0] = *a4;
    Vp = WinHvCreateVp(v12, a3, v18, a2, 0);
    if ( Vp >= 0 )
    {
      *((_BYTE *)v10 + 408) = 1;
      Vp = VidExoVppMapStatsPage((_DWORD)DeferredContext, a2, 0, (int)v10 + 104, (__int64)(v10 + 20));
      if ( Vp >= 0 )
      {
        Vp = VidExoVppMapStatsPage((_DWORD)DeferredContext, a2, 1, (int)v10 + 176, (__int64)(v10 + 22));
        if ( Vp >= 0 )
        {
          Vp = VidExoVppMapStatePage((__int64)DeferredContext, a2, (__int64)(v10 + 62), 0, v16, (__int64)(v10 + 80));
          if ( Vp >= 0 )
          {
            Vp = VidExoVppMapStatePage((__int64)DeferredContext, a2, (__int64)(v10 + 82), 1u, v17, (__int64)(v10 + 100));
            if ( Vp >= 0 )
            {
              *((_QWORD *)v10 + 9) = *a5;
              v14 = VidDeviceExtension;
              *a5 = 0;
              if ( (v14[162] & 0x20) == 0
                || (Vp = WinHvSetDispatchNotificationEvent(*((_QWORD *)DeferredContext + 81), a2, *((_QWORD *)v10 + 9)),
                    Vp >= 0) )
              {
                Vp = 0;
                *a6 = v10;
                return (unsigned int)Vp;
              }
              v13 = 978;
            }
            else
            {
              v13 = 960;
            }
          }
          else
          {
            v13 = 947;
          }
        }
        else
        {
          v13 = 931;
        }
      }
      else
      {
        v13 = 919;
      }
    }
    else
    {
      v13 = 902;
    }
    VidTraceErrorInternal0("VidExoVppCreate", "onecore\\vm\\vid\\sys\\driver\\videxovp.c", v13);
    VidExoVppDelete(DeferredContext, v10, 0);
  }
  else
  {
    VidTraceErrorInternal0("VidExoVppCreate", "onecore\\vm\\vid\\sys\\driver\\videxovp.c", 879);
    Vp = -1073741670;
  }
  VidTraceErrorStatusPartitionInternal0(
    (unsigned int)"VidExoVppCreate",
    (unsigned int)"onecore\\vm\\vid\\sys\\driver\\videxovp.c",
    994,
    Vp,
    (__int64)DeferredContext + 656);
  return (unsigned int)Vp;
}

```

## disassembly

```asm
0x140084884  mov     [rsp+arg_10], r8d
0x140084889  push    rbx
0x14008488a  push    rbp
0x14008488b  push    rsi
0x14008488c  push    rdi
0x14008488d  push    r12
0x14008488f  push    r13
0x140084891  push    r14
0x140084893  push    r15
0x140084895  sub     rsp, 48h
0x140084899  mov     ebp, edx
0x14008489b  mov     rsi, rcx
0x14008489e  mov     edx, 1A0h
0x1400848a3  mov     ecx, 40h ; '@'
0x1400848a8  mov     r8d, 72446456h
0x1400848ae  mov     rbx, r9
0x1400848b1  call    cs:__imp_ExAllocatePool2
0x1400848b8  nop     dword ptr [rax+rax+00h]
0x1400848bd  mov     rdi, rax
0x1400848c0  test    rax, rax
0x1400848c3  jnz     short loc_1400848E8
0x1400848c5  mov     r8d, 36Fh
0x1400848cb  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x1400848d2  lea     rcx, aVidexovppcreat; "VidExoVppCreate"
0x1400848d9  call    VidTraceErrorInternal0
0x1400848de  mov     ebx, 0C000009Ah
0x1400848e3  jmp     loc_140084AF1
0x1400848e8  mov     r12d, 48h ; 'H'
0x1400848ee  mov     [rax], ebp
0x1400848f0  mov     r8d, r12d; Size
0x1400848f3  lea     rcx, [rax+68h]; void *
0x1400848f7  xor     edx, edx; Val
0x1400848f9  call    memset
0x1400848fe  lea     rax, [rdi+90h]
0x140084905  mov     r8d, r12d; Size
0x140084908  lea     r15, [rdi+0B0h]
0x14008490f  mov     [rax+8], rax
0x140084913  mov     rcx, r15; void *
0x140084916  mov     [rax], rax
0x140084919  xor     edx, edx; Val
0x14008491b  call    memset
0x140084920  lea     rax, [r15+28h]
0x140084924  mov     r8d, r12d; Size
0x140084927  lea     r13, [rdi+0F8h]
0x14008492e  mov     [rax+8], rax
0x140084932  mov     rcx, r13; void *
0x140084935  mov     [rax], rax
0x140084938  xor     edx, edx; Val
0x14008493a  call    memset
0x14008493f  lea     rax, [r13+28h]
0x140084943  xor     edx, edx; Val
0x140084945  lea     r12, [rdi+148h]
0x14008494c  mov     [rax+8], rax
0x140084950  mov     rcx, r12; void *
0x140084953  mov     [rax], rax
0x140084956  lea     r8d, [rdx+48h]; Size
0x14008495a  call    memset
0x14008495f  lea     rax, [r12+28h]
0x140084964  mov     r8, rsi; DeferredContext
0x140084967  lea     rcx, [rdi+8]; Dpc
0x14008496b  mov     [rax+8], rax
0x14008496f  lea     rdx, VidExoVppInterceptDpcRoutine; DeferredRoutine
0x140084976  mov     [rax], rax
0x140084979  call    cs:__imp_KeInitializeDpc
0x140084980  nop     dword ptr [rax+rax+00h]
0x140084985  movups  xmm0, xmmword ptr [rbx]
0x140084988  mov     edx, [rsp+88h+arg_10]
0x14008498f  lea     r8, [rsp+88h+var_58]
0x140084994  mov     rcx, [rsi+288h]
0x14008499b  mov     r9d, ebp
0x14008499e  movdqu  [rsp+88h+var_58], xmm0
0x1400849a4  mov     [rsp+88h+var_68], 0
0x1400849ad  call    cs:__imp_WinHvCreateVp
0x1400849b4  nop     dword ptr [rax+rax+00h]
0x1400849b9  mov     ebx, eax
0x1400849bb  test    eax, eax
0x1400849bd  jns     short loc_1400849CA
0x1400849bf  mov     r8d, 386h
0x1400849c5  jmp     loc_140084ACC
0x1400849ca  lea     rax, [rdi+50h]
0x1400849ce  mov     byte ptr [rdi+198h], 1
0x1400849d5  lea     r9, [rdi+68h]
0x1400849d9  mov     [rsp+88h+var_68], rax
0x1400849de  xor     r8d, r8d
0x1400849e1  mov     edx, ebp
0x1400849e3  mov     rcx, rsi
0x1400849e6  call    VidExoVppMapStatsPage
0x1400849eb  mov     ebx, eax
0x1400849ed  test    eax, eax
0x1400849ef  jns     short loc_1400849FC
0x1400849f1  mov     r8d, 397h
0x1400849f7  jmp     loc_140084ACC
0x1400849fc  lea     rax, [rdi+58h]
0x140084a00  mov     r14d, 1
0x140084a06  mov     r8d, r14d
0x140084a09  mov     [rsp+88h+var_68], rax
0x140084a0e  mov     r9, r15
0x140084a11  mov     edx, ebp
0x140084a13  mov     rcx, rsi
0x140084a16  call    VidExoVppMapStatsPage
0x140084a1b  mov     ebx, eax
0x140084a1d  test    eax, eax
0x140084a1f  jns     short loc_140084A2C
0x140084a21  mov     r8d, 3A3h
0x140084a27  jmp     loc_140084ACC
0x140084a2c  lea     rax, [rdi+140h]
0x140084a33  xor     r9d, r9d
0x140084a36  mov     r8, r13
0x140084a39  mov     [rsp+88h+var_60], rax
0x140084a3e  mov     edx, ebp
0x140084a40  mov     rcx, rsi
0x140084a43  call    VidExoVppMapStatePage
0x140084a48  mov     ebx, eax
0x140084a4a  test    eax, eax
0x140084a4c  jns     short loc_140084A56
0x140084a4e  mov     r8d, 3B3h
0x140084a54  jmp     short loc_140084ACC
0x140084a56  lea     rax, [rdi+190h]
0x140084a5d  mov     r9d, r14d
0x140084a60  mov     r8, r12
0x140084a63  mov     [rsp+88h+var_60], rax
0x140084a68  mov     edx, ebp
0x140084a6a  mov     rcx, rsi
0x140084a6d  call    VidExoVppMapStatePage
0x140084a72  mov     ebx, eax
0x140084a74  test    eax, eax
0x140084a76  jns     short loc_140084A80
0x140084a78  mov     r8d, 3C0h
0x140084a7e  jmp     short loc_140084ACC
0x140084a80  mov     rcx, [rsp+88h+arg_20]
0x140084a88  mov     rax, [rcx]
0x140084a8b  mov     [rdi+48h], rax
0x140084a8f  mov     rax, cs:VidDeviceExtension
0x140084a96  mov     qword ptr [rcx], 0
0x140084a9d  mov     eax, [rax+288h]
0x140084aa3  test    al, 20h
0x140084aa5  jz      short loc_140084B1B
0x140084aa7  mov     r8, [rdi+48h]
0x140084aab  mov     edx, ebp
0x140084aad  mov     rcx, [rsi+288h]
0x140084ab4  call    cs:__imp_WinHvSetDispatchNotificationEvent
0x140084abb  nop     dword ptr [rax+rax+00h]
0x140084ac0  mov     ebx, eax
0x140084ac2  test    eax, eax
0x140084ac4  jns     short loc_140084B1B
0x140084ac6  mov     r8d, 3D2h
0x140084acc  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x140084ad3  lea     rcx, aVidexovppcreat; "VidExoVppCreate"
0x140084ada  call    VidTraceErrorInternal0
0x140084adf  xor     r8d, r8d
0x140084ae2  mov     rdx, rdi
0x140084ae5  mov     rcx, rsi
0x140084ae8  call    VidExoVppDelete
0x140084aed  test    ebx, ebx
0x140084aef  jns     short loc_140084B28
0x140084af1  lea     rax, [rsi+290h]
0x140084af8  mov     r9d, ebx
0x140084afb  mov     r8d, 3E2h
0x140084b01  mov     [rsp+88h+var_68], rax
0x140084b06  lea     rdx, aOnecoreVmVidSy_16; "onecore\\vm\\vid\\sys\\driver\\videxovp"...
0x140084b0d  lea     rcx, aVidexovppcreat; "VidExoVppCreate"
0x140084b14  call    VidTraceErrorStatusPartitionInternal0
0x140084b19  jmp     short loc_140084B28
0x140084b1b  mov     rax, [rsp+88h+arg_28]
0x140084b23  xor     ebx, ebx
0x140084b25  mov     [rax], rdi
0x140084b28  mov     eax, ebx
0x140084b2a  add     rsp, 48h
0x140084b2e  pop     r15
0x140084b30  pop     r14
0x140084b32  pop     r13
0x140084b34  pop     r12
0x140084b36  pop     rdi
0x140084b37  pop     rsi
0x140084b38  pop     rbp
0x140084b39  pop     rbx
0x140084b3a  retn
```
