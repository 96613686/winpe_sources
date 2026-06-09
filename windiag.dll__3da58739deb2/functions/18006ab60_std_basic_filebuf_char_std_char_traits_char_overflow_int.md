# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x18006ab60`
- end: `0x18006ace6`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004510`
- `0x18006ab60`

## import_xrefs

- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x18006ac6c`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x18006ac6c`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18006ac23`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18006ac23`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18006aca6`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18006aca6`

## pseudocode

```c
__int64 __fastcall std::filebuf::overflow(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  __int64 result; // rax
  _QWORD *v6; // rax
  int *v7; // rdx
  _QWORD *v8; // rdx
  _BYTE *v9; // r8
  _QWORD *v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  bool v15; // zf
  int v16; // eax
  int v17; // eax
  __int64 v18; // r14
  char v19; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v20[7]; // [rsp+41h] [rbp-3Fh] BYREF
  _BYTE *v21; // [rsp+48h] [rbp-38h] BYREF
  char *v22; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+78h] [rbp-8h] BYREF

  v2 = -1;
  if ( a2 == -1 )
    return 0;
  v6 = *(_QWORD **)(a1 + 64);
  if ( *v6 )
  {
    v7 = *(int **)(a1 + 88);
    if ( *v6 < (unsigned __int64)(*v6 + *v7) )
    {
      result = a2;
      --*v7;
      v8 = *(_QWORD **)(a1 + 64);
      v9 = (_BYTE *)(*v8)++;
      *v9 = a2;
      return result;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    v10 = *(_QWORD **)(a1 + 24);
    if ( *v10 == a1 + 112 )
    {
      v11 = *(_QWORD *)(a1 + 136);
      v12 = *(_QWORD *)(a1 + 144);
      *v10 = v11;
      **(_QWORD **)(a1 + 56) = v11;
      **(_DWORD **)(a1 + 80) = v12 - v11;
    }
    v13 = *(_QWORD *)(a1 + 104);
    if ( !v13 )
    {
      v14 = (unsigned int)(char)a2;
LABEL_11:
      v15 = (unsigned int)_o_fputc(v14, *(_QWORD *)(a1 + 128)) == -1;
LABEL_19:
      if ( !v15 )
        return a2;
      return v2;
    }
    v19 = a2;
    v22 = 0;
    v21 = 0;
    v16 = std::codecvt<char,char,_Mbstatet>::out(v13, a1 + 116, &v19, v20, &v22, v23, &v24, &v21);
    if ( !v16 || (v17 = v16 - 1) == 0 )
    {
      if ( v21 != v23 )
      {
        v18 = v21 - v23;
        if ( v18 != _o_fwrite(v23, 1, v21 - v23, *(_QWORD *)(a1 + 128)) )
          return v2;
      }
      *(_BYTE *)(a1 + 113) = 1;
      v15 = v22 == &v19;
      goto LABEL_19;
    }
    if ( v17 == 2 )
    {
      v14 = (unsigned int)v19;
      goto LABEL_11;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18006ab60  mov     [rsp-18h+arg_10], rbx
0x18006ab65  mov     [rsp-18h+arg_18], rsi
0x18006ab6a  push    rbp
0x18006ab6b  push    rdi
0x18006ab6c  push    r14
0x18006ab6e  mov     rbp, rsp
0x18006ab71  sub     rsp, 80h
0x18006ab78  mov     rax, cs:__security_cookie
0x18006ab7f  xor     rax, rsp
0x18006ab82  mov     [rbp+var_8], rax
0x18006ab86  or      edi, 0FFFFFFFFh
0x18006ab89  mov     esi, edx
0x18006ab8b  mov     rbx, rcx
0x18006ab8e  cmp     edx, edi
0x18006ab90  jnz     short loc_18006AB99
0x18006ab92  xor     eax, eax
0x18006ab94  jmp     loc_18006ACC2
0x18006ab99  mov     rax, [rcx+40h]
0x18006ab9d  xor     r14d, r14d
0x18006aba0  cmp     [rax], r14
0x18006aba3  jz      short loc_18006ABD5
0x18006aba5  mov     rdx, [rcx+58h]
0x18006aba9  movsxd  r8, dword ptr [rdx]
0x18006abac  mov     rcx, r8
0x18006abaf  add     rcx, [rax]
0x18006abb2  cmp     [rax], rcx
0x18006abb5  jnb     short loc_18006ABD5
0x18006abb7  lea     ecx, [r8-1]
0x18006abbb  mov     eax, esi
0x18006abbd  mov     [rdx], ecx
0x18006abbf  mov     rdx, [rbx+40h]
0x18006abc3  mov     r8, [rdx]
0x18006abc6  lea     rcx, [r8+1]
0x18006abca  mov     [rdx], rcx
0x18006abcd  mov     [r8], sil
0x18006abd0  jmp     loc_18006ACC2
0x18006abd5  cmp     [rbx+80h], r14
0x18006abdc  jz      loc_18006ACC0
0x18006abe2  mov     r8, [rbx+18h]
0x18006abe6  lea     rax, [rbx+70h]
0x18006abea  cmp     [r8], rax
0x18006abed  jnz     short loc_18006AC0F
0x18006abef  mov     rcx, [rbx+88h]
0x18006abf6  mov     rdx, [rbx+90h]
0x18006abfd  mov     [r8], rcx
0x18006ac00  sub     edx, ecx
0x18006ac02  mov     rax, [rbx+38h]
0x18006ac06  mov     [rax], rcx
0x18006ac09  mov     rax, [rbx+50h]
0x18006ac0d  mov     [rax], edx
0x18006ac0f  mov     rcx, [rbx+68h]
0x18006ac13  test    rcx, rcx
0x18006ac16  jnz     short loc_18006AC30
0x18006ac18  movsx   ecx, sil
0x18006ac1c  mov     rdx, [rbx+80h]
0x18006ac23  call    cs:__imp__o_fputc
0x18006ac29  cmp     eax, edi
0x18006ac2b  jmp     loc_18006ACBD
0x18006ac30  lea     rax, [rbp+var_38]
0x18006ac34  mov     [rbp+var_40], sil
0x18006ac38  mov     [rsp+80h+var_48], rax
0x18006ac3d  lea     rdx, [rbx+74h]
0x18006ac41  lea     rax, [rbp+var_8]
0x18006ac45  mov     [rbp+var_30], r14
0x18006ac49  mov     [rsp+80h+var_50], rax
0x18006ac4e  lea     r9, [rbp+var_3F]
0x18006ac52  lea     rax, [rbp+var_28]
0x18006ac56  mov     [rbp+var_38], r14
0x18006ac5a  mov     [rsp+80h+var_58], rax
0x18006ac5f  lea     r8, [rbp+var_40]
0x18006ac63  lea     rax, [rbp+var_30]
0x18006ac67  mov     [rsp+80h+var_60], rax
0x18006ac6c  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x18006ac72  test    eax, eax
0x18006ac74  jz      short loc_18006AC86
0x18006ac76  sub     eax, 1
0x18006ac79  jz      short loc_18006AC86
0x18006ac7b  cmp     eax, 2
0x18006ac7e  jnz     short loc_18006ACC0
0x18006ac80  movsx   ecx, [rbp+var_40]
0x18006ac84  jmp     short loc_18006AC1C
0x18006ac86  mov     r14, [rbp+var_38]
0x18006ac8a  lea     rax, [rbp+var_28]
0x18006ac8e  sub     r14, rax
0x18006ac91  jz      short loc_18006ACB1
0x18006ac93  mov     r9, [rbx+80h]
0x18006ac9a  lea     rcx, [rbp+var_28]
0x18006ac9e  mov     r8, r14
0x18006aca1  mov     edx, 1
0x18006aca6  call    cs:__imp__o_fwrite
0x18006acac  cmp     r14, rax
0x18006acaf  jnz     short loc_18006ACC0
0x18006acb1  lea     rax, [rbp+var_40]
0x18006acb5  mov     byte ptr [rbx+71h], 1
0x18006acb9  cmp     [rbp+var_30], rax
0x18006acbd  cmovnz  edi, esi
0x18006acc0  mov     eax, edi
0x18006acc2  mov     rcx, [rbp+var_8]
0x18006acc6  xor     rcx, rsp; StackCookie
0x18006acc9  call    __security_check_cookie
0x18006acce  lea     r11, [rsp+80h+var_s0]
0x18006acd6  mov     rbx, [r11+30h]
0x18006acda  mov     rsi, [r11+38h]
0x18006acde  mov     rsp, r11
0x18006ace1  pop     r14
0x18006ace3  pop     rdi
0x18006ace4  pop     rbp
0x18006ace5  retn
```
