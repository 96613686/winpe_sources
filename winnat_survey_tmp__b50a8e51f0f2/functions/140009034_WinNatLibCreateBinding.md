# WinNatLibCreateBinding

- ea: `0x140009034`
- end: `0x140009172`
- name: `WinNatLibCreateBinding`
- size: `318`
- prototype: `__int16 *__fastcall(_QWORD *, int, __int16 *, char, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400089d0`
- `0x14001a398`

## callees

- `0x140009034`
- `0x140009178`
- `0x14000e488`
- `0x14001f140`
- `0x14001f440`

## pseudocode

```c
__int16 *__fastcall WinNatLibCreateBinding(_QWORD *a1, int a2, __int16 *a3, char a4, __int64 a5, int a6)
{
  _QWORD *v8; // rcx
  __int64 v11; // rdx
  __int16 *v12; // rbx
  __int64 v13; // r8
  size_t v14; // r8
  __int16 *v15; // r9
  __int64 v16; // rcx
  __int16 v17; // ax
  __int64 v18; // rdx
  size_t v19; // r8
  __int16 v20; // cx
  int v21; // eax
  __int16 *result; // rax

  v8 = a1 + 1;
  if ( *a3 != 2 )
    v8 = a1;
  v12 = (__int16 *)PplAllocateFromLookasideList(*v8);
  if ( v12 )
  {
    v14 = 140;
    if ( *a3 != 2 )
      v14 = 152;
    memset(v12, 0, v14);
    v15 = v12 + 60;
    v16 = 5;
    *((_QWORD *)v12 + 12) = v12 + 60;
    v17 = *a3;
    v12[60] = *a3;
    *((_DWORD *)v12 + 23) = a2;
    if ( v17 != 2 )
      v16 = 11;
    v18 = 2;
    v19 = 4;
    *((_QWORD *)v12 + 13) = &v15[v16];
    v20 = *a3;
    *v15 = *a3;
    v12[61] = a3[1];
    if ( v20 != 2 )
      v19 = 16;
    if ( *a3 != 2 )
      v18 = 4;
    memmove(v12 + 62, &a3[v18], v19);
    *((_BYTE *)v12 + 68) = a4;
    *((_QWORD *)v12 + 10) = a1;
    *((_DWORD *)v12 + 16) = 0;
    if ( a4 == 6 )
    {
      v21 = *(_DWORD *)(a5 + 396);
    }
    else if ( a4 == 17 )
    {
      v21 = *(_DWORD *)(a5 + 392);
    }
    else
    {
      v21 = 1;
    }
    *((_DWORD *)v12 + 28) = v21;
    *((_DWORD *)v12 + 29) = a6;
    result = v12;
    *((_QWORD *)v12 + 1) = v12;
    *(_QWORD *)v12 = v12;
  }
  else
  {
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, v11, v13, L"Binding allocation failed");
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140009034  push    rbx
0x140009036  push    rbp
0x140009037  push    rsi
0x140009038  push    rdi
0x140009039  push    r14
0x14000903b  sub     rsp, 20h
0x14000903f  mov     rbp, rcx
0x140009042  mov     sil, r9b
0x140009045  add     rcx, 8
0x140009049  mov     rdi, r8
0x14000904c  cmp     word ptr [r8], 2
0x140009051  mov     r14d, edx
0x140009054  cmovnz  rcx, rbp
0x140009058  mov     rcx, [rcx]
0x14000905b  call    PplAllocateFromLookasideList
0x140009060  mov     rbx, rax
0x140009063  test    rax, rax
0x140009066  jz      loc_14000913C
0x14000906c  cmp     word ptr [rdi], 2
0x140009070  mov     eax, 98h
0x140009075  mov     rcx, rbx; void *
0x140009078  lea     r8d, [rax-0Ch]
0x14000907c  cmovnz  r8d, eax; Size
0x140009080  xor     edx, edx; Val
0x140009082  call    memset
0x140009087  lea     r9, [rbx+78h]
0x14000908b  mov     ecx, 0Ah
0x140009090  mov     [rbx+60h], r9
0x140009094  movzx   eax, word ptr [rdi]
0x140009097  mov     [r9], ax
0x14000909b  cmp     ax, 2
0x14000909f  lea     edx, [rcx+0Ch]
0x1400090a2  mov     [rbx+5Ch], r14d
0x1400090a6  cmovnz  ecx, edx
0x1400090a9  mov     edx, 4
0x1400090ae  add     rcx, r9
0x1400090b1  mov     r8d, edx
0x1400090b4  mov     [rbx+68h], rcx
0x1400090b8  movzx   ecx, word ptr [rdi]
0x1400090bb  mov     [r9], cx
0x1400090bf  cmp     cx, 2
0x1400090c3  movzx   eax, word ptr [rdi+2]
0x1400090c7  lea     rcx, [r9+4]; void *
0x1400090cb  mov     [r9+2], ax
0x1400090d0  lea     eax, [rdx+0Ch]
0x1400090d3  cmovnz  r8d, eax; Size
0x1400090d7  cmp     word ptr [rdi], 2
0x1400090db  lea     eax, [rdx+4]
0x1400090de  cmovnz  edx, eax
0x1400090e1  add     rdx, rdi; Src
0x1400090e4  call    memmove
0x1400090e9  mov     [rbx+44h], sil
0x1400090ed  mov     [rbx+50h], rbp
0x1400090f1  mov     dword ptr [rbx+40h], 0
0x1400090f8  cmp     sil, 6
0x1400090fc  jz      short loc_14000912F
0x1400090fe  cmp     sil, 11h
0x140009102  jnz     short loc_14000916B
0x140009104  mov     rax, [rsp+48h+arg_20]
0x140009109  mov     eax, [rax+188h]
0x14000910f  mov     [rbx+70h], eax
0x140009112  mov     eax, [rsp+48h+arg_28]
0x140009116  mov     [rbx+74h], eax
0x140009119  mov     rax, rbx
0x14000911c  mov     [rbx+8], rbx
0x140009120  mov     [rbx], rbx
0x140009123  add     rsp, 20h
0x140009127  pop     r14
0x140009129  pop     rdi
0x14000912a  pop     rsi
0x14000912b  pop     rbp
0x14000912c  pop     rbx
0x14000912d  retn
0x14000912f  mov     rax, [rsp+48h+arg_20]
0x140009134  mov     eax, [rax+18Ch]
0x14000913a  jmp     short loc_14000910F
0x14000913c  mov     eax, 1
0x140009141  cmp     cs:dword_140026104, eax
0x140009147  jz      short loc_14000914D
0x140009149  xor     eax, eax
0x14000914b  jmp     short loc_140009123
0x14000914d  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x140009154  jz      short loc_140009149
0x140009156  lea     r9, aBindingAllocat; "Binding allocation failed"
0x14000915d  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140009164  call    McTemplateK0z_EtwWriteTransfer
0x140009169  jmp     short loc_140009149
0x14000916b  mov     eax, 1
0x140009170  jmp     short loc_14000910F
```
