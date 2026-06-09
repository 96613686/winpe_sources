# SAXWriter::resolveState(SAXWriter::WRITER_STATE)

- ea: `0x10041ddd0`
- end: `0x10041defc`
- name: `?resolveState@SAXWriter@@MEAAJW4WRITER_STATE@1@@Z`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x10041ddd0`
- `0x100423e80`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall SAXWriter::resolveState(__int64 a1, int a2)
{
  int v4; // edi
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  bool v8; // zf
  int v9; // ecx

  v4 = 0;
  v5 = *(_DWORD *)(a1 + 68);
  if ( v5 )
  {
    v6 = v5 - 2;
    if ( !v6 )
    {
      switch ( a2 )
      {
        case 2:
        case 4:
        case 5:
        case 6:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 112LL))(a1);
          if ( *(_BYTE *)(a1 + 217) )
            goto LABEL_17;
          break;
        case 3:
          goto LABEL_19;
        default:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 112LL))(a1);
          break;
      }
      goto LABEL_19;
    }
    v7 = v6 - 5;
    if ( v7 )
    {
      if ( v7 != 1 || !*(_BYTE *)(a1 + 217) )
        goto LABEL_19;
      if ( a2 != 2 && a2 != 3 )
      {
        v9 = a2 - 4;
        v8 = a2 == 4;
LABEL_12:
        if ( !v8 && (unsigned int)(v9 - 1) > 1 )
          goto LABEL_19;
      }
    }
    else
    {
      if ( !*(_BYTE *)(a1 + 217) )
      {
LABEL_19:
        *(_DWORD *)(a1 + 68) = a2;
        return (unsigned int)v4;
      }
      if ( a2 != 2 )
      {
        v9 = a2 - 4;
        v8 = a2 == 4;
        goto LABEL_12;
      }
    }
LABEL_17:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 64LL))(a1);
    goto LABEL_19;
  }
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  if ( v4 >= 0 )
    goto LABEL_19;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x10041ddd0  mov     [rsp+arg_0], rbx
0x10041ddd5  mov     [rsp+arg_8], rsi
0x10041ddda  push    rdi
0x10041dddb  sub     rsp, 50h
0x10041dddf  mov     esi, edx
0x10041dde1  mov     rbx, rcx
0x10041dde4  xor     edi, edi
0x10041dde6  mov     [rsp+58h+var_30], edi
0x10041ddea  mov     ecx, [rcx+44h]
0x10041dded  test    ecx, ecx
0x10041ddef  jz      loc_10041DEA3
0x10041ddf5  sub     ecx, 2
0x10041ddf8  jz      short loc_10041DE55
0x10041ddfa  sub     ecx, 5
0x10041ddfd  jz      short loc_10041DE26
0x10041ddff  cmp     ecx, 1
0x10041de02  jnz     loc_10041DEC5; jumptable 000000010041DE70 case 3
0x10041de08  cmp     [rbx+0D9h], dil
0x10041de0f  jz      loc_10041DEC5; jumptable 000000010041DE70 case 3
0x10041de15  mov     ecx, edx
0x10041de17  sub     ecx, 2
0x10041de1a  jz      short loc_10041DE49
0x10041de1c  sub     ecx, 1
0x10041de1f  jz      short loc_10041DE49
0x10041de21  sub     ecx, 1
0x10041de24  jmp     short loc_10041DE3D
0x10041de26  cmp     byte ptr [rbx+0D9h], 0
0x10041de2d  jz      loc_10041DEC5; jumptable 000000010041DE70 case 3
0x10041de33  mov     ecx, esi
0x10041de35  sub     ecx, 2
0x10041de38  jz      short loc_10041DE49
0x10041de3a  sub     ecx, 2
0x10041de3d  jz      short loc_10041DE49
0x10041de3f  sub     ecx, 1
0x10041de42  jz      short loc_10041DE49
0x10041de44  cmp     ecx, 1
0x10041de47  jnz     short loc_10041DEC5; jumptable 000000010041DE70 case 3
0x10041de49  mov     rax, [rbx]
0x10041de4c  mov     rcx, rbx
0x10041de4f  mov     rax, [rax+40h]
0x10041de53  jmp     short loc_10041DEBF
0x10041de55  lea     eax, [rdx-2]; switch 6 cases
0x10041de58  cmp     eax, 5
0x10041de5b  ja      short def_10041DE70; jumptable 000000010041DE70 default case, case 7
0x10041de5d  cdqe
0x10041de5f  lea     rdx, __ImageBase
0x10041de66  mov     ecx, ds:(jpt_10041DE70 - 100400000h)[rdx+rax*4]
0x10041de6d  add     rcx, rdx
0x10041de70  jmp     rcx; switch jump
0x10041de72  mov     rax, [rbx]; jumptable 000000010041DE70 cases 2,4-6
0x10041de75  mov     rcx, rbx
0x10041de78  mov     rax, [rax+70h]
0x10041de7c  call    cs:__guard_dispatch_icall_fptr
0x10041de82  cmp     byte ptr [rbx+0D9h], 0
0x10041de89  jz      short loc_10041DEC5; jumptable 000000010041DE70 case 3
0x10041de8b  mov     rax, [rbx]
0x10041de8e  mov     rcx, rbx
0x10041de91  mov     rax, [rax+40h]
0x10041de95  jmp     short loc_10041DEBF
0x10041de97  mov     rax, [rbx]; jumptable 000000010041DE70 default case, case 7
0x10041de9a  mov     rcx, rbx
0x10041de9d  mov     rax, [rax+70h]
0x10041dea1  jmp     short loc_10041DEBF
0x10041dea3  mov     rax, [rbx]
0x10041dea6  mov     rcx, rbx
0x10041dea9  mov     rax, [rax+20h]
0x10041dead  call    cs:__guard_dispatch_icall_fptr
0x10041deb3  mov     edi, eax
0x10041deb5  mov     [rsp+58h+var_30], eax
0x10041deb9  test    eax, eax
0x10041debb  jns     short loc_10041DEC5; jumptable 000000010041DE70 case 3
0x10041debd  jmp     short loc_10041DED2
0x10041debf  call    cs:__guard_dispatch_icall_fptr
0x10041dec5  mov     [rbx+44h], esi; jumptable 000000010041DE70 case 3
0x10041dec8  jmp     short loc_10041DED2
0x10041deca  mov     edi, [rsp+58h+var_38]
0x10041dece  mov     [rsp+58h+var_30], edi
0x10041ded2  mov     eax, edi
0x10041ded4  mov     rbx, [rsp+58h+arg_0]
0x10041ded9  mov     rsi, [rsp+58h+arg_8]
0x10041dede  add     rsp, 50h
0x10041dee2  pop     rdi
0x10041dee3  retn
0x10043a070  push    rbp
0x10043a072  sub     rsp, 20h
0x10043a076  mov     rbp, rdx
0x10043a079  mov     [rbp+40h], rcx
0x10043a07d  mov     [rbp+38h], rcx
0x10043a081  mov     rax, [rbp+38h]
0x10043a085  mov     rcx, [rax]
0x10043a088  mov     [rbp+30h], rcx
0x10043a08c  mov     rax, [rbp+30h]
0x10043a090  mov     eax, [rax]
0x10043a092  cmp     eax, 0C0000005h
0x10043a097  jz      short loc_10043A0C9
0x10043a099  add     eax, 1FFFFFFFh
0x10043a09e  cmp     eax, 1
0x10043a0a1  ja      short loc_10043A0B9
0x10043a0a3  mov     rax, [rbp+30h]
0x10043a0a7  cmp     dword ptr [rax+18h], 1
0x10043a0ab  jnz     short loc_10043A0B9
0x10043a0ad  mov     rax, [rbp+30h]
0x10043a0b1  mov     ecx, [rax+20h]
0x10043a0b4  mov     [rbp+20h], ecx
0x10043a0b7  jmp     short loc_10043A0C0
0x10043a0b9  mov     dword ptr [rbp+20h], 8000FFFFh
0x10043a0c0  mov     dword ptr [rbp+24h], 1
0x10043a0c7  jmp     short loc_10043A0D0
0x10043a0c9  mov     dword ptr [rbp+24h], 0
0x10043a0d0  mov     eax, [rbp+24h]
0x10043a0d3  add     rsp, 20h
0x10043a0d7  pop     rbp
0x10043a0d8  retn
```
