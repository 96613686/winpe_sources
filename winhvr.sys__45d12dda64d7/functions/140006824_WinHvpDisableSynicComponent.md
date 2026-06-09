# WinHvpDisableSynicComponent

- ea: `0x140006824`
- end: `0x1400068b8`
- name: `WinHvpDisableSynicComponent`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400067ac`
- `0x140006998`

## callees

- `0x140001460`
- `0x140005d3c`
- `0x140006824`
- `0x140006c74`

## import_xrefs

- `ntoskrnl!MmUnmapIoSpace` at `0x140006878`
- `ntoskrnl!MmUnmapIoSpace` at `0x140006878`

## pseudocode

```c
void __fastcall WinHvpDisableSynicComponent(__int64 a1, unsigned int a2)
{
  bool v2; // zf
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_BYTE *)(a1 + 18) == 0;
  v5 = 0;
  if ( !v2 )
  {
    if ( (int)WinHvpGetVpRegister64Self2(a2, &v5) >= 0 )
      WinHvpSetVpRegister64Self2(a2, v5 & 0xFFFFFFFFFFFFFFFEuLL, 0);
    *(_BYTE *)(a1 + 18) = 0;
  }
  if ( *(_BYTE *)(a1 + 17) )
  {
    MmUnmapIoSpace(*(PVOID *)(a1 + 8), 0x1000u);
    *(_BYTE *)(a1 + 17) = 0;
  }
  if ( *(_BYTE *)(a1 + 16) )
  {
    WinHvpFreeOverlayPages(*(_QWORD *)(a1 + 8));
    *(_BYTE *)(a1 + 16) = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x140006824  mov     [rsp+arg_8], rbx
0x140006829  push    rdi
0x14000682a  sub     rsp, 20h
0x14000682e  cmp     byte ptr [rcx+12h], 0
0x140006832  mov     edi, edx
0x140006834  mov     rbx, rcx
0x140006837  mov     [rsp+28h+arg_0], 0
0x140006840  jz      short loc_140006869
0x140006842  lea     rdx, [rsp+28h+arg_0]
0x140006847  mov     ecx, edi
0x140006849  call    WinHvpGetVpRegister64Self2
0x14000684e  test    eax, eax
0x140006850  js      short loc_140006865
0x140006852  mov     rdx, [rsp+28h+arg_0]
0x140006857  xor     r8d, r8d
0x14000685a  and     rdx, 0FFFFFFFFFFFFFFFEh
0x14000685e  mov     ecx, edi
0x140006860  call    WinHvpSetVpRegister64Self2
0x140006865  mov     byte ptr [rbx+12h], 0
0x140006869  cmp     byte ptr [rbx+11h], 0
0x14000686d  jz      short loc_140006888
0x14000686f  mov     rcx, [rbx+8]; BaseAddress
0x140006873  mov     edx, 1000h; NumberOfBytes
0x140006878  call    cs:__imp_MmUnmapIoSpace
0x14000687f  nop     dword ptr [rax+rax+00h]
0x140006884  mov     byte ptr [rbx+11h], 0
0x140006888  cmp     byte ptr [rbx+10h], 0
0x14000688c  jz      short loc_14000689D
0x14000688e  mov     rcx, [rbx+8]
0x140006892  xor     edx, edx
0x140006894  call    WinHvpFreeOverlayPages
0x140006899  mov     byte ptr [rbx+10h], 0
0x14000689d  mov     qword ptr [rbx+8], 0
0x1400068a5  mov     qword ptr [rbx], 0
0x1400068ac  mov     rbx, [rsp+28h+arg_8]
0x1400068b1  add     rsp, 20h
0x1400068b5  pop     rdi
0x1400068b6  retn
```
