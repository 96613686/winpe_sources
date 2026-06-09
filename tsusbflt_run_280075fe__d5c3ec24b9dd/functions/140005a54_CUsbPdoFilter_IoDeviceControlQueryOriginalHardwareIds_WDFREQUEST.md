# CUsbPdoFilter::IoDeviceControlQueryOriginalHardwareIds(WDFREQUEST__ *)

- ea: `0x140005a54`
- end: `0x140005d1d`
- name: `?IoDeviceControlQueryOriginalHardwareIds@CUsbPdoFilter@@AEAAXPEAUWDFREQUEST__@@@Z`
- size: `713`
- prototype: `void __fastcall(CUsbPdoFilter *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140009930`

## callees

- `0x140005a54`
- `0x14000a90c`
- `0x14000a9f0`
- `0x14000aa30`
- `0x14000ab00`
- `0x14000b140`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005cec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005cec`

## pseudocode

```c
void __fastcall CUsbPdoFilter::IoDeviceControlQueryOriginalHardwareIds(CUsbPdoFilter *this, struct WDFREQUEST__ *a2)
{
  struct _LIST_ENTRY *Blink; // rax
  unsigned __int16 *v5; // rdi
  int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r8
  int v10; // eax
  int v11; // eax
  size_t v12; // rbx
  unsigned int v13; // [rsp+30h] [rbp-79h] BYREF
  unsigned __int16 **v14; // [rsp+38h] [rbp-71h] BYREF
  void *v15; // [rsp+40h] [rbp-69h] BYREF
  _DWORD *v16; // [rsp+48h] [rbp-61h] BYREF
  size_t Size; // [rsp+50h] [rbp-59h] BYREF
  __int64 v18; // [rsp+58h] [rbp-51h] BYREF
  __int128 v19; // [rsp+60h] [rbp-49h] BYREF
  __int128 v20; // [rsp+70h] [rbp-39h] BYREF
  __int128 v21; // [rsp+80h] [rbp-29h]
  __int64 v22; // [rsp+90h] [rbp-19h]
  _DWORD v23[18]; // [rsp+98h] [rbp-11h] BYREF

  v16 = 0;
  v15 = 0;
  v18 = 0;
  v14 = 0;
  v22 = 0;
  v20 = 0;
  v21 = 0;
  memset(v23, 0, sizeof(v23));
  v19 = 0;
  Blink = WPP_MAIN_CB.Queue.ListEntry.Flink[134].Blink;
  v5 = 0;
  v13 = 0;
  Size = 0;
  if ( ((int (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, _DWORD **, __int64 *))Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         4,
         &v16,
         &v18) < 0 )
    goto LABEL_14;
  v6 = 1;
  if ( !*v16 )
    goto LABEL_5;
  if ( *v16 != 1 )
  {
LABEL_14:
    v9 = 3221225488LL;
    goto LABEL_15;
  }
  v6 = 2;
LABEL_5:
  if ( ((int (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, void **))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         0,
         &v15) < 0 )
  {
    v15 = 0;
    v14 = 0;
  }
  v22 = 0;
  v20 = 0;
  LOWORD(v20) = 40;
  v21 = 0;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[133].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    &v20);
  LOWORD(v23[0]) = 4891;
  v23[2] = v6;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _DWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    v23);
  v7 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[142].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2);
  *(_DWORD *)(v7 + 48) = -1073741637;
  *(_QWORD *)(v7 + 56) = 0;
  v8 = *((_QWORD *)this + 6);
  v19 = 0x200000010uLL;
  if ( ((unsigned __int8 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, __int128 *))WPP_MAIN_CB.Queue.ListEntry.Flink[126].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         v8,
         &v19) )
  {
    v10 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.Queue.ListEntry.Flink[127].Flink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            a2);
    v9 = (unsigned int)v10;
    if ( v10 >= 0 )
    {
      v5 = (unsigned __int16 *)((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[138].Flink)(
                                 WPP_MAIN_CB.Queue.ListEntry.Blink,
                                 a2,
                                 (unsigned int)v10);
      v11 = ValidateMultiStrings(v5, 0xFFFFu, &v13, &Size, (const unsigned __int16 ***)&v14);
      v9 = (unsigned int)v11;
      if ( v11 >= 0 )
      {
        v12 = Size;
        if ( (unsigned __int64)v14 >= Size )
        {
          memmove(v15, v5, Size);
          v9 = 0;
        }
        else
        {
          v9 = 2147483653LL;
        }
        goto LABEL_16;
      }
    }
  }
  else
  {
    v9 = 2147483665LL;
  }
LABEL_15:
  v12 = 0;
LABEL_16:
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, size_t))WPP_MAIN_CB.Queue.ListEntry.Flink[132].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    v9,
    v12);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
}

```

## disassembly

```asm
0x140005a54  mov     [rsp-8+arg_10], rbx
0x140005a59  mov     [rsp-8+arg_18], rsi
0x140005a5e  push    rbp
0x140005a5f  push    rdi
0x140005a60  push    r14
0x140005a62  lea     rbp, [rsp-47h]
0x140005a67  sub     rsp, 0F0h
0x140005a6e  mov     rax, cs:__security_cookie
0x140005a75  xor     rax, rsp
0x140005a78  mov     [rbp+57h+var_20], rax
0x140005a7c  xor     eax, eax
0x140005a7e  mov     [rbp+57h+var_B8], 0
0x140005a86  xorps   xmm0, xmm0
0x140005a89  mov     [rbp+57h+var_C0], 0
0x140005a91  mov     rsi, rdx
0x140005a94  mov     [rbp+57h+var_A8], 0
0x140005a9c  mov     r14, rcx
0x140005a9f  mov     [rbp+57h+var_C8], 0
0x140005aa7  lea     r8d, [rax+48h]; Size
0x140005aab  mov     [rbp+57h+var_70], rax
0x140005aaf  xor     edx, edx; Val
0x140005ab1  lea     rcx, [rbp+57h+var_68]; void *
0x140005ab5  movups  [rbp+57h+var_90], xmm0
0x140005ab9  movups  [rbp+57h+var_80], xmm0
0x140005abd  call    memset
0x140005ac2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140005ac9  lea     rcx, [rbp+57h+var_A8]
0x140005acd  xorps   xmm0, xmm0
0x140005ad0  mov     [rsp+100h+var_E0], rcx
0x140005ad5  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140005adc  lea     r9, [rbp+57h+var_B8]
0x140005ae0  movups  [rbp+57h+var_A0], xmm0
0x140005ae4  mov     rax, [rax+868h]
0x140005aeb  xor     edi, edi
0x140005aed  mov     rdx, rsi
0x140005af0  mov     [rbp+57h+var_D0], 0
0x140005af7  mov     [rbp+57h+Size], 0
0x140005aff  lea     r8d, [rdi+4]
0x140005b03  call    _guard_dispatch_icall
0x140005b08  test    eax, eax
0x140005b0a  js      loc_140005CBA
0x140005b10  mov     rax, [rbp+57h+var_B8]
0x140005b14  lea     ebx, [rdi+1]
0x140005b17  mov     ecx, [rax]
0x140005b19  test    ecx, ecx
0x140005b1b  jz      short loc_140005B28
0x140005b1d  cmp     ecx, ebx
0x140005b1f  jnz     loc_140005CBA
0x140005b25  lea     ebx, [rdi+2]
0x140005b28  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140005b2f  lea     rcx, [rbp+57h+var_C8]
0x140005b33  mov     [rsp+100h+var_E0], rcx; unsigned __int16 ***
0x140005b38  lea     r9, [rbp+57h+var_C0]
0x140005b3c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140005b43  xor     r8d, r8d
0x140005b46  mov     rdx, rsi
0x140005b49  mov     rax, [rax+870h]
0x140005b50  call    _guard_dispatch_icall
0x140005b55  test    eax, eax
0x140005b57  jns     short loc_140005B61
0x140005b59  mov     [rbp+57h+var_C0], rdi
0x140005b5d  mov     [rbp+57h+var_C8], rdi
0x140005b61  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140005b68  lea     r8, [rbp+57h+var_90]
0x140005b6c  xor     eax, eax
0x140005b6e  xorps   xmm0, xmm0
0x140005b71  mov     [rbp+57h+var_70], rax
0x140005b75  mov     rdx, rsi
0x140005b78  movups  [rbp+57h+var_90], xmm0
0x140005b7c  mov     eax, 28h ; '('
0x140005b81  mov     word ptr [rbp+57h+var_90], ax
0x140005b85  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140005b8c  movups  [rbp+57h+var_80], xmm0
0x140005b90  mov     rax, [rax+850h]
0x140005b97  call    _guard_dispatch_icall
0x140005b9c  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140005ba3  lea     r8, [rbp+57h+var_68]
0x140005ba7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140005bae  mov     rdx, rsi
0x140005bb1  mov     [rbp+57h+var_68], 131Bh
0x140005bb7  mov     [rbp+57h+var_60], ebx
0x140005bba  mov     rax, [rax+7E0h]
0x140005bc1  call    _guard_dispatch_icall
0x140005bc6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140005bcd  mov     rdx, rsi
0x140005bd0  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140005bd7  mov     rax, [rax+8E8h]
0x140005bde  call    _guard_dispatch_icall
0x140005be3  lea     r9, [rbp+57h+var_A0]
0x140005be7  mov     rdx, rsi
0x140005bea  mov     dword ptr [rax+30h], 0C00000BBh
0x140005bf1  mov     [rax+38h], rdi
0x140005bf5  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140005bfc  mov     r8, [r14+30h]
0x140005c00  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140005c07  mov     qword ptr [rbp+57h+var_A0+8], rdi
0x140005c0b  mov     dword ptr [rbp+57h+var_A0], 10h
0x140005c12  mov     dword ptr [rbp+57h+var_A0+4], 2
0x140005c19  mov     rax, [rax+7E8h]
0x140005c20  call    _guard_dispatch_icall
0x140005c25  test    al, al
0x140005c27  jnz     short loc_140005C34
0x140005c29  mov     r8d, 80000011h
0x140005c2f  jmp     loc_140005CC0
0x140005c34  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140005c3b  mov     rdx, rsi
0x140005c3e  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140005c45  mov     rax, [rax+7F0h]
0x140005c4c  call    _guard_dispatch_icall
0x140005c51  mov     r8d, eax
0x140005c54  test    eax, eax
0x140005c56  js      short loc_140005CC0
0x140005c58  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140005c5f  mov     rdx, rsi
0x140005c62  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140005c69  mov     rax, [rax+8A0h]
0x140005c70  call    _guard_dispatch_icall
0x140005c75  lea     r9, [rbp+57h+Size]; unsigned __int64 *
0x140005c79  mov     edx, 0FFFFh; unsigned __int64
0x140005c7e  lea     r8, [rbp+57h+var_D0]; unsigned int *
0x140005c82  mov     rcx, rax; unsigned __int16 *
0x140005c85  mov     rdi, rax
0x140005c88  call    ?ValidateMultiStrings@@YAJPEBG_KPEAKPEA_KPEAPEAPEBG@Z; ValidateMultiStrings(ushort const *,unsigned __int64,ulong *,unsigned __int64 *,ushort const * * *)
0x140005c8d  mov     r8d, eax
0x140005c90  test    eax, eax
0x140005c92  js      short loc_140005CC0
0x140005c94  mov     rbx, [rbp+57h+Size]
0x140005c98  cmp     [rbp+57h+var_C8], rbx
0x140005c9c  jnb     short loc_140005CA6
0x140005c9e  mov     r8d, 80000005h
0x140005ca4  jmp     short loc_140005CC2
0x140005ca6  mov     rcx, [rbp+57h+var_C0]; void *
0x140005caa  mov     r8, rbx; Size
0x140005cad  mov     rdx, rdi; Src
0x140005cb0  call    memmove
0x140005cb5  xor     r8d, r8d
0x140005cb8  jmp     short loc_140005CC2
0x140005cba  mov     r8d, 0C0000010h
0x140005cc0  xor     ebx, ebx
0x140005cc2  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140005cc9  mov     r9, rbx
0x140005ccc  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140005cd3  mov     rdx, rsi
0x140005cd6  mov     rax, [rax+848h]
0x140005cdd  call    _guard_dispatch_icall
0x140005ce2  test    rdi, rdi
0x140005ce5  jz      short loc_140005CF8
0x140005ce7  xor     edx, edx; Tag
0x140005ce9  mov     rcx, rdi; P
0x140005cec  call    cs:__imp_ExFreePoolWithTag
0x140005cf3  nop     dword ptr [rax+rax+00h]
0x140005cf8  mov     rcx, [rbp+57h+var_20]
0x140005cfc  xor     rcx, rsp; StackCookie
0x140005cff  call    __security_check_cookie
0x140005d04  lea     r11, [rsp+100h+var_10]
0x140005d0c  mov     rbx, [r11+30h]
0x140005d10  mov     rsi, [r11+38h]
0x140005d14  mov     rsp, r11
0x140005d17  pop     r14
0x140005d19  pop     rdi
0x140005d1a  pop     rbp
0x140005d1b  retn
```
