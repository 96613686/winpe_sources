# WinHvpEnableSynicComponent

- ea: `0x140006998`
- end: `0x140006a83`
- name: `WinHvpEnableSynicComponent`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400068c0`

## callees

- `0x140001460`
- `0x140005be4`
- `0x140005ec0`
- `0x140006824`
- `0x140006998`
- `0x140006c74`

## import_xrefs

- `ntoskrnl!MmGetPhysicalAddress` at `0x140006a12`
- `ntoskrnl!MmGetPhysicalAddress` at `0x140006a12`

## pseudocode

```c
__int64 __fastcall WinHvpEnableSynicComponent(__int64 a1, unsigned int a2)
{
  __int64 result; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // esi
  __int16 v8; // bx
  void *OverlayPages; // rax
  unsigned __int64 v10; // rcx
  __int64 v11; // [rsp+68h] [rbp+20h] BYREF

  v11 = 0;
  result = WinHvpGetVpRegister64Self2(a2, &v11);
  v7 = result;
  if ( (int)result >= 0 )
  {
    v8 = v11;
    if ( WinHvpCpuManagement || WinHvpNested || (v11 & 1) != 0 )
    {
      v10 = v11 & 0xFFFFFFFFFFFFF000uLL;
      LOBYTE(v6) = 1;
      *(_QWORD *)a1 = v11 & 0xFFFFFFFFFFFFF000uLL;
      v7 = WinHvpValidateAndMapOverlayAddress(v10, v5, v6, a1 + 8);
      if ( v7 < 0 )
        goto LABEL_7;
      *(_BYTE *)(a1 + 17) = 1;
    }
    else
    {
      OverlayPages = (void *)WinHvpAllocateOverlayPages(1);
      *(_QWORD *)(a1 + 8) = OverlayPages;
      if ( !OverlayPages )
      {
        v7 = -1073741670;
        goto LABEL_7;
      }
      *(_BYTE *)(a1 + 16) = 1;
      *(PHYSICAL_ADDRESS *)a1 = MmGetPhysicalAddress(OverlayPages);
    }
    *(_BYTE *)(a1 + 18) = 0;
    if ( (v8 & 1) != 0 )
      return (unsigned int)v7;
    v7 = WinHvpSetVpRegister64Self2(a2, v8 & 0xFFE | *(_QWORD *)a1 & 0xFFFFFFFFFFFFF000uLL | 1, 0);
    if ( v7 >= 0 )
    {
      *(_BYTE *)(a1 + 18) = 1;
      return (unsigned int)v7;
    }
LABEL_7:
    WinHvpDisableSynicComponent(a1, a2);
    return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x140006998  push    rbx
0x14000699a  push    rbp
0x14000699b  push    rsi
0x14000699c  push    rdi
0x14000699d  sub     rsp, 28h
0x1400069a1  mov     ebp, edx
0x1400069a3  mov     [rsp+48h+arg_18], 0
0x1400069ac  mov     rdi, rcx
0x1400069af  lea     rdx, [rsp+48h+arg_18]
0x1400069b4  mov     ecx, ebp
0x1400069b6  call    WinHvpGetVpRegister64Self2
0x1400069bb  mov     esi, eax
0x1400069bd  test    eax, eax
0x1400069bf  js      short loc_140006A01
0x1400069c1  cmp     cs:WinHvpCpuManagement, 0
0x1400069c8  mov     rbx, [rsp+48h+arg_18]
0x1400069cd  jnz     short loc_140006A23
0x1400069cf  cmp     cs:WinHvpNested, 0
0x1400069d6  jnz     short loc_140006A23
0x1400069d8  test    bl, 1
0x1400069db  jnz     short loc_140006A23
0x1400069dd  mov     ecx, 1
0x1400069e2  call    WinHvpAllocateOverlayPages
0x1400069e7  mov     [rdi+8], rax
0x1400069eb  test    rax, rax
0x1400069ee  jnz     short loc_140006A0B
0x1400069f0  mov     esi, 0C000009Ah
0x1400069f5  mov     edx, ebp
0x1400069f7  mov     rcx, rdi
0x1400069fa  call    WinHvpDisableSynicComponent
0x1400069ff  mov     eax, esi
0x140006a01  add     rsp, 28h
0x140006a05  pop     rdi
0x140006a06  pop     rsi
0x140006a07  pop     rbp
0x140006a08  pop     rbx
0x140006a09  retn
0x140006a0b  mov     rcx, rax; BaseAddress
0x140006a0e  mov     byte ptr [rdi+10h], 1
0x140006a12  call    cs:__imp_MmGetPhysicalAddress
0x140006a19  nop     dword ptr [rax+rax+00h]
0x140006a1e  mov     [rdi], rax
0x140006a21  jmp     short loc_140006A46
0x140006a23  mov     rcx, rbx
0x140006a26  lea     r9, [rdi+8]
0x140006a2a  and     rcx, 0FFFFFFFFFFFFF000h
0x140006a31  mov     r8b, 1
0x140006a34  mov     [rdi], rcx
0x140006a37  call    WinHvpValidateAndMapOverlayAddress
0x140006a3c  mov     esi, eax
0x140006a3e  test    eax, eax
0x140006a40  js      short loc_1400069F5
0x140006a42  mov     byte ptr [rdi+11h], 1
0x140006a46  mov     byte ptr [rdi+12h], 0
0x140006a4a  test    bl, 1
0x140006a4d  jnz     short loc_1400069FF
0x140006a4f  mov     rdx, [rdi]
0x140006a52  and     ebx, 0FFEh
0x140006a58  and     rdx, 0FFFFFFFFFFFFF000h
0x140006a5f  xor     r8d, r8d
0x140006a62  or      rdx, rbx
0x140006a65  mov     ecx, ebp
0x140006a67  or      rdx, 1
0x140006a6b  call    WinHvpSetVpRegister64Self2
0x140006a70  mov     esi, eax
0x140006a72  test    eax, eax
0x140006a74  js      loc_1400069F5
0x140006a7a  mov     byte ptr [rdi+12h], 1
0x140006a7e  jmp     loc_1400069FF
```
