# USBD_ValidateConfigurationDescriptorInternal

- ea: `0x14000bb28`
- end: `0x14000bf66`
- name: `USBD_ValidateConfigurationDescriptorInternal`
- size: `1086`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002ca84`

## callees

- `0x14000bb28`
- `0x140015100`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bea7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bea7`
- `ntoskrnl!ExAllocatePool2` at `0x14000bbc7`
- `ntoskrnl!ExAllocatePool2` at `0x14000bbea`
- `ntoskrnl!ExAllocatePool2` at `0x14000bbc7`
- `ntoskrnl!ExAllocatePool2` at `0x14000bbea`

## pseudocode

```c
__int64 __fastcall USBD_ValidateConfigurationDescriptorInternal(
        unsigned __int8 *a1,
        unsigned int a2,
        unsigned __int16 a3,
        _QWORD *a4)
{
  unsigned __int8 *v5; // rsi
  unsigned __int8 *v6; // rbp
  unsigned int v7; // ecx
  int v8; // edx
  int v9; // ebx
  char *Pool2; // r14
  _BYTE *v11; // r13
  unsigned __int8 *v12; // rdi
  int v13; // r10d
  unsigned __int8 *v14; // rcx
  char v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rbp
  __int64 v20; // r15
  __int64 v21; // rcx
  int v23; // ecx
  unsigned __int8 *v24; // [rsp+20h] [rbp-48h]
  int v25; // [rsp+70h] [rbp+8h]
  _QWORD *v26; // [rsp+88h] [rbp+20h]
  char v27; // [rsp+90h] [rbp+28h]

  v26 = a4;
  v5 = a1;
  if ( a1 && a2 >= 9 && a4 )
  {
    if ( *a1 < 9u )
    {
      v9 = -1072693247;
      goto LABEL_40;
    }
    if ( a1[1] != 2 )
    {
      v9 = -1072693246;
      v5 = a1 + 1;
      goto LABEL_40;
    }
    v6 = a1 + 2;
    v7 = *((unsigned __int16 *)a1 + 1);
    if ( v7 > a2 || (v8 = v5[4], v7 < 9 * (v8 + 1)) )
    {
      v9 = -1072693242;
      v5 = v6;
      goto LABEL_40;
    }
    v9 = 0;
    if ( a3 > 1u && (_BYTE)v8 )
    {
      Pool2 = (char *)ExAllocatePool2(64, 516, 1130525525);
      if ( Pool2 )
      {
        v11 = (_BYTE *)ExAllocatePool2(64, 256, 1130525525);
        if ( v11 )
        {
          v12 = v5 + 9;
          v13 = 0;
          v27 = 1;
          v14 = &v5[*(unsigned __int16 *)v6];
          v25 = 0;
          v24 = v14;
          v15 = 1;
          while ( v12 < v14 )
          {
            if ( (unsigned __int64)(v14 - v12) < 2 )
            {
              v9 = -1072693248;
              goto LABEL_35;
            }
            v16 = *v12;
            if ( &v12[v16] > v14 )
              goto LABEL_58;
            switch ( v12[1] )
            {
              case 4u:
                if ( (unsigned __int8)v16 < 9u || (_BYTE)v16 != 9 && a3 >= 3u )
                {
LABEL_58:
                  v9 = -1072693247;
                  goto LABEL_35;
                }
                v18 = v12[2];
                v19 = v12[3];
                if ( v15 )
                {
                  if ( (_BYTE)v19 )
                    goto LABEL_66;
                  v15 = 0;
                  *Pool2 = v18;
                  *(_WORD *)(Pool2 + 1) = 256;
                  LOWORD(v13) = v13 + 1;
                  Pool2[514] = v12[4];
                  Pool2[515] = 0;
                  v11[v18] = 1;
                  v25 = v13;
                  v27 = 0;
                }
                else
                {
                  if ( (_BYTE)v18 == *Pool2 )
                  {
                    v20 = v12[3];
                    if ( Pool2[v19 + 2] == 1 || (unsigned __int8)Pool2[1] >= (unsigned __int8)v19 && a3 >= 3u )
                    {
LABEL_66:
                      v9 = -1072693245;
                      v12 += 3;
                      goto LABEL_35;
                    }
                  }
                  else
                  {
                    if ( v11[v18] == 1 || (unsigned __int8)*Pool2 > (unsigned __int8)v18 && a3 >= 3u )
                    {
                      v9 = -1072693245;
                      v12 += 2;
                      goto LABEL_35;
                    }
                    if ( (_BYTE)v19 )
                      goto LABEL_66;
                    v11[v18] = 1;
                    *Pool2 = v18;
                    LOWORD(v13) = v13 + 1;
                    v25 = v13;
                    memset(Pool2 + 2, 0, 0x100u);
                    v20 = 0;
                  }
                  if ( Pool2[515] != Pool2[514] && a3 >= 3u )
                  {
                    v9 = -1072693240;
                    goto LABEL_35;
                  }
                  memset(Pool2 + 258, 0, 0x100u);
                  v13 = v25;
                  v15 = v27;
                  Pool2[515] = 0;
                  Pool2[514] = v12[4];
                  Pool2[v20 + 2] = 1;
                  Pool2[1] = v19;
                }
                break;
              case 5u:
                if ( (unsigned __int8)v16 < 7u || (_BYTE)v16 != 7 && a3 >= 3u )
                  goto LABEL_58;
                if ( v15 )
                {
                  v9 = -1072693244;
                  goto LABEL_35;
                }
                v21 = v12[2];
                if ( Pool2[v21 + 258] )
                {
                  v9 = -1072693239;
                  v12 += 2;
                  goto LABEL_35;
                }
                Pool2[v21 + 258] = 1;
                ++Pool2[515];
                break;
              case 0xBu:
                if ( (_BYTE)v16 != 8
                  || (v23 = v12[3], v23 + (unsigned int)v12[2] > 0x100)
                  || (unsigned __int8)v23 > v5[4]
                  || !(_BYTE)v23 )
                {
                  v9 = -1072693243;
                  goto LABEL_35;
                }
                break;
            }
            v17 = *v12;
            if ( !(_BYTE)v17 )
              break;
            v14 = v24;
            v12 += v17;
          }
          v12 = 0;
          if ( (_WORD)v13 == v5[4] )
            goto LABEL_35;
          v9 = -1072693241;
        }
        else
        {
          v9 = -1073737728;
        }
        v12 = v5;
LABEL_35:
        v5 = v12;
        ExFreePoolWithTag(Pool2, 0);
        if ( v11 )
          ExFreePoolWithTag(v11, 0);
        if ( v9 >= 0 )
        {
          a4 = v26;
          goto LABEL_39;
        }
      }
      else
      {
        v9 = -1073737728;
      }
      a4 = v26;
      goto LABEL_40;
    }
LABEL_39:
    v5 = 0;
LABEL_40:
    *a4 = v5;
    return (unsigned int)v9;
  }
  return 3221237760LL;
}

```

## disassembly

```asm
0x14000bb28  mov     [rsp+arg_8], rbx
0x14000bb2d  mov     [rsp+arg_18], r9
0x14000bb32  push    rbp
0x14000bb33  push    rsi
0x14000bb34  push    rdi
0x14000bb35  push    r12
0x14000bb37  push    r13
0x14000bb39  push    r14
0x14000bb3b  push    r15
0x14000bb3d  sub     rsp, 30h
0x14000bb41  movzx   r12d, r8w
0x14000bb45  mov     rsi, rcx
0x14000bb48  test    rcx, rcx
0x14000bb4b  jz      loc_14000BE98
0x14000bb51  cmp     edx, 9
0x14000bb54  jb      loc_14000BE98
0x14000bb5a  test    r9, r9
0x14000bb5d  jz      loc_14000BE98
0x14000bb63  cmp     byte ptr [rcx], 9
0x14000bb66  jb      loc_14000BE42
0x14000bb6c  cmp     byte ptr [rcx+1], 2
0x14000bb70  jnz     loc_14000BECC
0x14000bb76  lea     rbp, [rcx+2]
0x14000bb7a  movzx   ecx, word ptr [rbp+0]
0x14000bb7e  cmp     ecx, edx
0x14000bb80  ja      loc_14000BF59
0x14000bb86  movzx   edx, byte ptr [rsi+4]
0x14000bb8a  mov     r15d, 1
0x14000bb90  lea     eax, [r15+rdx]
0x14000bb94  lea     eax, [rax+rax*8]
0x14000bb97  cmp     ecx, eax
0x14000bb99  jb      loc_14000BF59
0x14000bb9f  xor     ebx, ebx
0x14000bba1  cmp     r8w, r15w
0x14000bba5  jbe     loc_14000BD9F
0x14000bbab  test    dl, dl
0x14000bbad  jz      loc_14000BD9F
0x14000bbb3  mov     edi, 43627355h
0x14000bbb8  lea     r13d, [r15+3Fh]
0x14000bbbc  mov     r8d, edi
0x14000bbbf  mov     ecx, r13d
0x14000bbc2  mov     edx, 204h
0x14000bbc7  call    cs:__imp_ExAllocatePool2
0x14000bbce  nop     dword ptr [rax+rax+00h]
0x14000bbd3  mov     r14, rax
0x14000bbd6  test    rax, rax
0x14000bbd9  jz      loc_14000BE4C
0x14000bbdf  mov     r8d, edi
0x14000bbe2  mov     edx, 100h
0x14000bbe7  mov     ecx, r13d
0x14000bbea  call    cs:__imp_ExAllocatePool2
0x14000bbf1  nop     dword ptr [rax+rax+00h]
0x14000bbf6  mov     r13, rax
0x14000bbf9  test    rax, rax
0x14000bbfc  jz      loc_14000BE8B
0x14000bc02  movzx   ecx, word ptr [rbp+0]
0x14000bc06  lea     rdi, [rsi+9]
0x14000bc0a  xor     r10d, r10d
0x14000bc0d  mov     [rsp+68h+arg_20], r15b
0x14000bc15  add     rcx, rsi
0x14000bc18  mov     [rsp+68h+arg_0], r10d
0x14000bc1d  mov     [rsp+68h+var_48], rcx
0x14000bc22  mov     r8b, r15b
0x14000bc25  cmp     rdi, rcx
0x14000bc28  jnb     loc_14000BD62
0x14000bc2e  mov     rax, rcx
0x14000bc31  sub     rax, rdi
0x14000bc34  cmp     rax, 2
0x14000bc38  jb      loc_14000BEC2
0x14000bc3e  movzx   edx, byte ptr [rdi]
0x14000bc41  lea     rax, [rdi+rdx]
0x14000bc45  cmp     rax, rcx
0x14000bc48  ja      loc_14000BEB8
0x14000bc4e  movzx   ecx, byte ptr [rdi+1]
0x14000bc52  sub     ecx, 4
0x14000bc55  jz      short loc_14000BC7E
0x14000bc57  sub     ecx, 1
0x14000bc5a  jz      loc_14000BD24
0x14000bc60  cmp     ecx, 6
0x14000bc63  jz      loc_14000BE5E
0x14000bc69  movzx   eax, byte ptr [rdi]
0x14000bc6c  test    al, al
0x14000bc6e  jz      loc_14000BD62
0x14000bc74  mov     rcx, [rsp+68h+var_48]
0x14000bc79  add     rdi, rax
0x14000bc7c  jmp     short loc_14000BC25
0x14000bc7e  cmp     dl, 9
0x14000bc81  jb      loc_14000BEB8
0x14000bc87  jnz     loc_14000BEE6
0x14000bc8d  lea     rcx, [rdi+2]
0x14000bc91  movzx   edx, byte ptr [rcx]
0x14000bc94  lea     rax, [rdi+3]
0x14000bc98  movzx   ebp, byte ptr [rax]
0x14000bc9b  test    r8b, r8b
0x14000bc9e  jnz     loc_14000BE01
0x14000bca4  mov     r8b, [r14]
0x14000bca7  cmp     dl, r8b
0x14000bcaa  jnz     loc_14000BDBC
0x14000bcb0  cmp     byte ptr [rbp+r14+2], 1
0x14000bcb6  mov     r15d, ebp
0x14000bcb9  jz      loc_14000BEFD
0x14000bcbf  cmp     [r14+1], bpl
0x14000bcc3  jnb     loc_14000BEF2
0x14000bcc9  mov     al, [r14+202h]
0x14000bcd0  cmp     [r14+203h], al
0x14000bcd7  jnz     loc_14000BF22
0x14000bcdd  lea     rcx, [r14+102h]; void *
0x14000bce4  xor     edx, edx; Val
0x14000bce6  mov     r8d, 100h; Size
0x14000bcec  call    memset
0x14000bcf1  mov     r10d, [rsp+68h+arg_0]
0x14000bcf6  mov     r8b, [rsp+68h+arg_20]
0x14000bcfe  mov     [r14+203h], bl
0x14000bd05  mov     al, [rdi+4]
0x14000bd08  mov     [r14+202h], al
0x14000bd0f  mov     byte ptr [r15+r14+2], 1
0x14000bd15  mov     r15d, 1
0x14000bd1b  mov     [r14+1], bpl
0x14000bd1f  jmp     loc_14000BC69
0x14000bd24  cmp     dl, 7
0x14000bd27  jb      loc_14000BEB8
0x14000bd2d  jnz     loc_14000BEDA
0x14000bd33  test    r8b, r8b
0x14000bd36  jnz     loc_14000BF45
0x14000bd3c  movzx   ecx, byte ptr [rdi+2]
0x14000bd40  cmp     [rcx+r14+102h], bl
0x14000bd48  jnz     loc_14000BF37
0x14000bd4e  mov     [rcx+r14+102h], r15b
0x14000bd56  add     [r14+203h], r15b
0x14000bd5d  jmp     loc_14000BC69
0x14000bd62  movzx   eax, byte ptr [rsi+4]
0x14000bd66  xor     edi, edi
0x14000bd68  cmp     r10w, ax
0x14000bd6c  jnz     loc_14000BF4F
0x14000bd72  xor     edx, edx; Tag
0x14000bd74  mov     rcx, r14; P
0x14000bd77  mov     rsi, rdi
0x14000bd7a  call    cs:__imp_ExFreePoolWithTag
0x14000bd81  nop     dword ptr [rax+rax+00h]
0x14000bd86  test    r13, r13
0x14000bd89  jnz     loc_14000BEA2
0x14000bd8f  test    ebx, ebx
0x14000bd91  js      loc_14000BE51
0x14000bd97  mov     r9, [rsp+68h+arg_18]
0x14000bd9f  xor     esi, esi
0x14000bda1  mov     [r9], rsi
0x14000bda4  mov     eax, ebx
0x14000bda6  mov     rbx, [rsp+68h+arg_8]
0x14000bdab  add     rsp, 30h
0x14000bdaf  pop     r15
0x14000bdb1  pop     r14
0x14000bdb3  pop     r13
0x14000bdb5  pop     r12
0x14000bdb7  pop     rdi
0x14000bdb8  pop     rsi
0x14000bdb9  pop     rbp
0x14000bdba  retn
0x14000bdbc  cmp     [rdx+r13], r15b
0x14000bdc0  jz      loc_14000BF15
0x14000bdc6  cmp     r8b, dl
0x14000bdc9  ja      loc_14000BF0A
0x14000bdcf  test    bpl, bpl
0x14000bdd2  jnz     loc_14000BEFD
0x14000bdd8  mov     [rdx+r13], r15b
0x14000bddc  lea     rcx, [r14+2]; void *
0x14000bde0  mov     [r14], dl
0x14000bde3  add     r10w, r15w
0x14000bde7  xor     edx, edx; Val
0x14000bde9  mov     [rsp+68h+arg_0], r10d
0x14000bdee  mov     r8d, 100h; Size
0x14000bdf4  call    memset
0x14000bdf9  xor     r15d, r15d
0x14000bdfc  jmp     loc_14000BCC9
0x14000be01  test    bpl, bpl
0x14000be04  jnz     loc_14000BEFD
0x14000be0a  xor     r8b, r8b
0x14000be0d  mov     [r14], dl
0x14000be10  mov     word ptr [r14+1], 100h
0x14000be17  add     r10w, r15w
0x14000be1b  mov     al, [rdi+4]
0x14000be1e  mov     [r14+202h], al
0x14000be25  mov     [r14+203h], bl
0x14000be2c  mov     [rdx+r13], r15b
0x14000be30  mov     [rsp+68h+arg_0], r10d
0x14000be35  mov     [rsp+68h+arg_20], r8b
0x14000be3d  jmp     loc_14000BC69
0x14000be42  mov     ebx, 0C0100001h
0x14000be47  jmp     loc_14000BDA1
0x14000be4c  mov     ebx, 0C0001000h
0x14000be51  mov     r9, [rsp+68h+arg_18]
0x14000be59  jmp     loc_14000BDA1
0x14000be5e  cmp     dl, 8
0x14000be61  jnz     short loc_14000BE81
0x14000be63  movzx   ecx, byte ptr [rdi+3]
0x14000be67  movzx   eax, byte ptr [rdi+2]
0x14000be6b  add     eax, ecx
0x14000be6d  cmp     eax, 100h
0x14000be72  ja      short loc_14000BE81
0x14000be74  cmp     cl, [rsi+4]
0x14000be77  ja      short loc_14000BE81
0x14000be79  test    cl, cl
0x14000be7b  jnz     loc_14000BC69
0x14000be81  mov     ebx, 0C0100005h
0x14000be86  jmp     loc_14000BD72
0x14000be8b  mov     ebx, 0C0001000h
0x14000be90  mov     rdi, rsi
0x14000be93  jmp     loc_14000BD72
0x14000be98  mov     eax, 0C0003000h
0x14000be9d  jmp     loc_14000BDA6
0x14000bea2  xor     edx, edx; Tag
0x14000bea4  mov     rcx, r13; P
0x14000bea7  call    cs:__imp_ExFreePoolWithTag
0x14000beae  nop     dword ptr [rax+rax+00h]
0x14000beb3  jmp     loc_14000BD8F
0x14000beb8  mov     ebx, 0C0100001h
0x14000bebd  jmp     loc_14000BD72
0x14000bec2  mov     ebx, 0C0100000h
0x14000bec7  jmp     loc_14000BD72
0x14000becc  mov     ebx, 0C0100002h
0x14000bed1  lea     rsi, [rcx+1]
0x14000bed5  jmp     loc_14000BDA1
0x14000beda  cmp     r12w, 3
0x14000bedf  jnb     short loc_14000BEB8
0x14000bee1  jmp     loc_14000BD33
0x14000bee6  cmp     r12w, 3
0x14000beeb  jnb     short loc_14000BEB8
0x14000beed  jmp     loc_14000BC8D
0x14000bef2  cmp     r12w, 3
0x14000bef7  jb      loc_14000BCC9
0x14000befd  mov     ebx, 0C0100003h
0x14000bf02  mov     rdi, rax
0x14000bf05  jmp     loc_14000BD72
0x14000bf0a  cmp     r12w, 3
0x14000bf0f  jb      loc_14000BDCF
0x14000bf15  mov     ebx, 0C0100003h
0x14000bf1a  mov     rdi, rcx
0x14000bf1d  jmp     loc_14000BD72
0x14000bf22  cmp     r12w, 3
0x14000bf27  jb      loc_14000BCDD
0x14000bf2d  mov     ebx, 0C0100008h
0x14000bf32  jmp     loc_14000BD72
0x14000bf37  mov     ebx, 0C0100009h
0x14000bf3c  add     rdi, 2
0x14000bf40  jmp     loc_14000BD72
0x14000bf45  mov     ebx, 0C0100004h
0x14000bf4a  jmp     loc_14000BD72
0x14000bf4f  mov     ebx, 0C0100007h
0x14000bf54  jmp     loc_14000BE90
0x14000bf59  mov     ebx, 0C0100006h
0x14000bf5e  mov     rsi, rbp
0x14000bf61  jmp     loc_14000BDA1
```
