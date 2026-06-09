# FilterOidRequestComplete

- ea: `0x14000ae50`
- end: `0x14000aedb`
- name: `FilterOidRequestComplete`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000ae50`
- `0x14000aef0`
- `0x14000d8ec`
- `0x14000d91c`

## pseudocode

```c
void __fastcall FilterOidRequestComplete(__int64 a1, __int64 a2, unsigned int a3)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 187, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  FilterOidRequestCompleteCommon(a1, a2, a3, 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 188, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
}

```

## disassembly

```asm
0x14000ae50  push    rbx
0x14000ae52  push    rbp
0x14000ae53  push    rsi
0x14000ae54  push    rdi
0x14000ae55  sub     rsp, 28h
0x14000ae59  mov     ebx, r8d
0x14000ae5c  mov     rdi, rdx
0x14000ae5f  mov     rsi, rcx
0x14000ae62  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae69  lea     rbp, WPP_GLOBAL_Control
0x14000ae70  cmp     rcx, rbp
0x14000ae73  jz      short loc_14000AE7C
0x14000ae75  mov     eax, [rcx+2Ch]
0x14000ae78  test    al, 20h
0x14000ae7a  jnz     short loc_14000AEAA
0x14000ae7c  mov     r9b, 1
0x14000ae7f  mov     r8d, ebx
0x14000ae82  mov     rdx, rdi
0x14000ae85  mov     rcx, rsi
0x14000ae88  call    FilterOidRequestCompleteCommon
0x14000ae8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae94  cmp     rcx, rbp
0x14000ae97  jz      short loc_14000AEA0
0x14000ae99  mov     eax, [rcx+2Ch]
0x14000ae9c  test    al, 20h
0x14000ae9e  jnz     short loc_14000AEC1
0x14000aea0  add     rsp, 28h
0x14000aea4  pop     rdi
0x14000aea5  pop     rsi
0x14000aea6  pop     rbp
0x14000aea7  pop     rbx
0x14000aea8  retn
0x14000aeaa  mov     rcx, [rcx+18h]
0x14000aeae  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000aeb5  mov     edx, 0BBh
0x14000aeba  call    WPP_SF_
0x14000aebf  jmp     short loc_14000AE7C
0x14000aec1  mov     rcx, [rcx+18h]
0x14000aec5  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000aecc  mov     edx, 0BCh
0x14000aed1  xor     r9d, r9d
0x14000aed4  call    WPP_SF_d
0x14000aed9  jmp     short loc_14000AEA0
```
