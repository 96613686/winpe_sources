# Srv2AllocateWorkItem

- ea: `0x140005f20`
- end: `0x140006211`
- name: `Srv2AllocateWorkItem`
- size: `753`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400055b0`

## callees

- `0x140005470`
- `0x140005f20`
- `0x14000ab3c`
- `0x140038980`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006096`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006096`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400061d8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400061d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400060f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400061a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400060f2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400061a2`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140005f61`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140005f61`
- `ntoskrnl!EtwActivityIdControl` at `0x140006153`
- `ntoskrnl!EtwActivityIdControl` at `0x140006153`
- `HAL!KeQueryPerformanceCounter` at `0x140006049`
- `HAL!KeQueryPerformanceCounter` at `0x140006133`
- `HAL!KeQueryPerformanceCounter` at `0x140006049`
- `HAL!KeQueryPerformanceCounter` at `0x140006133`

## pseudocode

```c
char *__fastcall Srv2AllocateWorkItem(__int64 a1)
{
  int LockArray_high; // edi
  struct _LOOKASIDE_LIST_EX *v3; // rbx
  char *result; // rax
  char *v5; // rbx
  __int64 v6; // rax
  bool v7; // zf
  LARGE_INTEGER PerformanceCounter; // rax
  KIRQL v9; // cl
  _QWORD *v10; // r8
  int v11; // edi
  __int64 v12; // rcx
  struct _LOOKASIDE_LIST_EX *v13; // rdi

  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v3 = (struct _LOOKASIDE_LIST_EX *)((char *)qword_140058148 + 128 * (unsigned __int64)(unsigned __int16)LockArray_high);
  if ( !LOBYTE(v3[3].L.Depth) )
    PplpLazyInitializeLookasideList(qword_140058148, &v3[2]);
  result = (char *)ExAllocateFromLookasideListEx(v3 + 2);
  v5 = result;
  if ( result )
  {
    v6 = *(_QWORD *)(a1 + 64);
    *((_DWORD *)v5 + 2) = 5;
    *((_DWORD *)v5 + 3) = 220;
    *((_WORD *)v5 + 8) = 1888;
    *(_QWORD *)v5 = 1;
    *((_QWORD *)v5 + 6) = 0;
    *((_QWORD *)v5 + 7) = v5;
    *((_QWORD *)v5 + 8) = v6;
    *((_QWORD *)v5 + 11) = Srv2ProcPostToCallback;
    *((_DWORD *)v5 + 18) = 0;
    *((_QWORD *)v5 + 12) = a1;
    v7 = byte_140058150 == 0;
    *((_QWORD *)v5 + 47) = MEMORY[0xFFFFF78000000014];
    if ( v7 )
      *((_QWORD *)v5 + 48) = 0;
    else
      *((LARGE_INTEGER *)v5 + 48) = KeQueryPerformanceCounter(0);
    *((_DWORD *)v5 + 98) = *(_DWORD *)(a1 + 504);
    *((_WORD *)v5 + 198) = LockArray_high;
    memset(v5 + 400, 0, 0xA0u);
    *((_WORD *)v5 + 356) = 0;
    v5[714] = 0;
    *(_OWORD *)(v5 + 584) = 0;
    *(_OWORD *)(v5 + 600) = 0;
    *(_OWORD *)(v5 + 616) = 0;
    *(_OWORD *)(v5 + 632) = 0;
    *(_OWORD *)(v5 + 648) = 0;
    *(_OWORD *)(v5 + 664) = 0;
    *(_OWORD *)(v5 + 680) = 0;
    *(_OWORD *)(v5 + 696) = 0;
    PerformanceCounter = KeQueryPerformanceCounter(0);
    *((LARGE_INTEGER *)v5 + 90) = PerformanceCounter;
    *((LARGE_INTEGER *)v5 + 91) = PerformanceCounter;
    *((_QWORD *)v5 + 92) = MEMORY[0xFFFFF78000000014];
    *((_QWORD *)v5 + 94) = v5;
    if ( (Microsoft_Windows_SMBServerEnableBits & 8) != 0 )
    {
      EtwActivityIdControl(3u, (LPGUID)(v5 + 584));
      v5[600] = 1;
      if ( (Microsoft_Windows_SMBServerEnableBits & 8) != 0 )
        McTemplateK0x_EtwWriteTransfer(v12, &SMB2_EVENT_WORKITEM_START, v5 + 584, v5 + 584);
    }
    else
    {
      v5[600] = 0;
    }
    v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 184));
    if ( *(_DWORD *)(a1 + 12) == 220 )
    {
      v10 = *(_QWORD **)(a1 + 200);
      if ( *v10 != a1 + 192 )
        __fastfail(3u);
      *((_QWORD *)v5 + 13) = a1 + 192;
      *((_QWORD *)v5 + 14) = v10;
      *v10 = v5 + 104;
      *(_QWORD *)(a1 + 200) = v5 + 104;
      v11 = *(_DWORD *)(a1 + 208);
      *(_DWORD *)(a1 + 208) = v11 + 1;
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 184), v9);
      if ( !v11 && ((_InterlockedExchangeAdd64((volatile signed __int64 *)a1, 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        __int2c();
      return v5;
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 184), v9);
      v13 = (struct _LOOKASIDE_LIST_EX *)((char *)qword_140058148
                                        + 128 * (unsigned __int64)*((unsigned __int16 *)v5 + 198));
      if ( !LOBYTE(v13[3].L.Depth) )
        PplpLazyInitializeLookasideList(qword_140058148, &v13[2]);
      ExFreeToLookasideListEx(v13 + 2, v5);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140005f20  mov     [rsp+arg_10], rbx
0x140005f25  mov     [rsp+arg_18], rsi
0x140005f2a  push    rdi
0x140005f2b  sub     rsp, 20h
0x140005f2f  mov     edi, gs:1A4h
0x140005f37  mov     rsi, rcx
0x140005f3a  mov     rcx, cs:qword_140058148
0x140005f41  movzx   ebx, di
0x140005f44  shl     rbx, 7
0x140005f48  add     rbx, rcx
0x140005f4b  movzx   eax, byte ptr [rbx+130h]
0x140005f52  test    al, al
0x140005f54  jz      loc_1400061EB
0x140005f5a  lea     rcx, [rbx+0C0h]; Lookaside
0x140005f61  call    cs:__imp_ExAllocateFromLookasideListEx
0x140005f68  nop     dword ptr [rax+rax+00h]
0x140005f6d  mov     rbx, rax
0x140005f70  test    rax, rax
0x140005f73  jz      loc_140006187
0x140005f79  mov     rax, [rsi+40h]
0x140005f7d  xor     ecx, ecx; PerformanceFrequency
0x140005f7f  mov     dword ptr [rbx+8], 5
0x140005f86  mov     dword ptr [rbx+0Ch], 0DCh
0x140005f8d  mov     word ptr [rbx+10h], 760h
0x140005f93  mov     [rsp+28h+arg_0], rbp
0x140005f98  mov     ebp, 1
0x140005f9d  mov     [rbx], rbp
0x140005fa0  mov     [rbx+30h], rcx
0x140005fa4  mov     [rbx+38h], rbx
0x140005fa8  mov     [rbx+40h], rax
0x140005fac  lea     rax, Srv2ProcPostToCallback
0x140005fb3  mov     [rbx+58h], rax
0x140005fb7  mov     [rbx+48h], ecx
0x140005fba  mov     [rbx+60h], rsi
0x140005fbe  mov     rax, ds:0FFFFF78000000014h
0x140005fc8  cmp     cs:byte_140058150, cl
0x140005fce  mov     [rbx+178h], rax
0x140005fd5  mov     [rsp+28h+arg_8], r14
0x140005fda  jnz     loc_140006133
0x140005fe0  mov     [rbx+180h], rcx
0x140005fe7  mov     eax, [rsi+1F8h]
0x140005fed  lea     rcx, [rbx+190h]; void *
0x140005ff4  xor     edx, edx; Val
0x140005ff6  mov     [rbx+188h], eax
0x140005ffc  mov     r8d, 0A0h; Size
0x140006002  mov     [rbx+18Ch], di
0x140006009  call    memset
0x14000600e  lea     rdi, [rbx+248h]
0x140006015  xorps   xmm0, xmm0
0x140006018  mov     word ptr [rdi+80h], 0
0x140006021  xor     ecx, ecx; PerformanceFrequency
0x140006023  mov     byte ptr [rdi+82h], 0
0x14000602a  movups  xmmword ptr [rdi], xmm0
0x14000602d  movups  xmmword ptr [rdi+10h], xmm0
0x140006031  movups  xmmword ptr [rdi+20h], xmm0
0x140006035  movups  xmmword ptr [rdi+30h], xmm0
0x140006039  movups  xmmword ptr [rdi+40h], xmm0
0x14000603d  movups  xmmword ptr [rdi+50h], xmm0
0x140006041  movups  xmmword ptr [rdi+60h], xmm0
0x140006045  movups  xmmword ptr [rdi+70h], xmm0
0x140006049  call    cs:__imp_KeQueryPerformanceCounter
0x140006050  nop     dword ptr [rax+rax+00h]
0x140006055  mov     [rdi+88h], rax
0x14000605c  mov     [rdi+90h], rax
0x140006063  mov     rax, 0FFFFF78000000014h
0x14000606d  mov     rax, [rax]
0x140006070  mov     [rdi+98h], rax
0x140006077  mov     [rdi+0A8h], rbx
0x14000607e  test    cs:Microsoft_Windows_SMBServerEnableBits, 8
0x140006085  jnz     loc_14000614B
0x14000608b  mov     byte ptr [rdi+10h], 0
0x14000608f  lea     rcx, [rsi+0B8h]; SpinLock
0x140006096  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000609d  nop     dword ptr [rax+rax+00h]
0x1400060a2  cmp     dword ptr [rsi+0Ch], 0DCh
0x1400060a9  movzx   ecx, al
0x1400060ac  jnz     loc_140006198
0x1400060b2  lea     rdx, [rsi+0C0h]
0x1400060b9  mov     r8, [rdx+8]
0x1400060bd  cmp     [r8], rdx
0x1400060c0  jnz     loc_14000620A
0x1400060c6  mov     [rbx+68h], rdx
0x1400060ca  lea     rax, [rbx+68h]
0x1400060ce  mov     [rax+8], r8
0x1400060d2  mov     [r8], rax
0x1400060d5  mov     [rdx+8], rax
0x1400060d9  movzx   edx, cl; NewIrql
0x1400060dc  mov     edi, [rsi+0D0h]
0x1400060e2  lea     rcx, [rsi+0B8h]; SpinLock
0x1400060e9  lea     eax, [rdi+1]
0x1400060ec  mov     [rsi+0D0h], eax
0x1400060f2  call    cs:__imp_KeReleaseSpinLock
0x1400060f9  nop     dword ptr [rax+rax+00h]
0x1400060fe  test    edi, edi
0x140006100  jnz     short loc_140006115
0x140006102  lock xadd [rsi], rbp
0x140006107  lea     rax, [rbp+2]
0x14000610b  test    rax, 0FFFFFFFFFFFFFFFEh
0x140006111  jnz     short loc_140006115
0x140006113  int     2Ch; Windows NT - assertion failure
0x140006115  mov     rax, rbx
0x140006118  mov     rbp, [rsp+28h+arg_0]
0x14000611d  mov     r14, [rsp+28h+arg_8]
0x140006122  mov     rbx, [rsp+28h+arg_10]
0x140006127  mov     rsi, [rsp+28h+arg_18]
0x14000612c  add     rsp, 20h
0x140006130  pop     rdi
0x140006131  retn
0x140006133  call    cs:__imp_KeQueryPerformanceCounter
0x14000613a  nop     dword ptr [rax+rax+00h]
0x14000613f  mov     [rbx+180h], rax
0x140006146  jmp     loc_140005FE7
0x14000614b  mov     rdx, rdi; ActivityId
0x14000614e  mov     ecx, 3; ControlCode
0x140006153  call    cs:__imp_EtwActivityIdControl
0x14000615a  nop     dword ptr [rax+rax+00h]
0x14000615f  mov     [rdi+10h], bpl
0x140006163  test    cs:Microsoft_Windows_SMBServerEnableBits, 8
0x14000616a  jz      loc_14000608F
0x140006170  mov     r9, rdi
0x140006173  lea     rdx, SMB2_EVENT_WORKITEM_START
0x14000617a  mov     r8, rdi
0x14000617d  call    McTemplateK0x_EtwWriteTransfer
0x140006182  jmp     loc_14000608F
0x140006187  mov     rbx, [rsp+28h+arg_10]
0x14000618c  mov     rsi, [rsp+28h+arg_18]
0x140006191  add     rsp, 20h
0x140006195  pop     rdi
0x140006196  retn
0x140006198  movzx   edx, cl; NewIrql
0x14000619b  lea     rcx, [rsi+0B8h]; SpinLock
0x1400061a2  call    cs:__imp_KeReleaseSpinLock
0x1400061a9  nop     dword ptr [rax+rax+00h]
0x1400061ae  movzx   edi, word ptr [rbx+18Ch]
0x1400061b5  mov     rcx, cs:qword_140058148
0x1400061bc  shl     rdi, 7
0x1400061c0  add     rdi, rcx
0x1400061c3  movzx   eax, byte ptr [rdi+130h]
0x1400061ca  test    al, al
0x1400061cc  jz      short loc_1400061FC
0x1400061ce  mov     rdx, rbx; Entry
0x1400061d1  lea     rcx, [rdi+0C0h]; Lookaside
0x1400061d8  call    cs:__imp_ExFreeToLookasideListEx
0x1400061df  nop     dword ptr [rax+rax+00h]
0x1400061e4  xor     eax, eax
0x1400061e6  jmp     loc_140006118
0x1400061eb  lea     rdx, [rbx+0C0h]
0x1400061f2  call    PplpLazyInitializeLookasideList
0x1400061f7  jmp     loc_140005F5A
0x1400061fc  lea     rdx, [rdi+0C0h]
0x140006203  call    PplpLazyInitializeLookasideList
0x140006208  jmp     short loc_1400061CE
0x14000620a  mov     ecx, 3
0x14000620f  int     29h; Win8: RtlFailFast(ecx)
```
