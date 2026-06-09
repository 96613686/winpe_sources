# ValidateMSXUPayloadsFaceAuth(_HW_DEVICE_EXTENSION *,uchar const *,ushort)

- ea: `0x14005a820`
- end: `0x14005abb1`
- name: `?ValidateMSXUPayloadsFaceAuth@@YAJPEAU_HW_DEVICE_EXTENSION@@PEBEG@Z`
- size: `913`
- prototype: `__int64 __fastcall(struct _HW_DEVICE_EXTENSION *, const unsigned __int8 *, unsigned __int16)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1400051e4`
- `0x1400053fc`
- `0x14005a820`
- `0x14005c69c`
- `0x14005c6d0`

## pseudocode

```c
__int64 __fastcall ValidateMSXUPayloadsFaceAuth(
        struct _HW_DEVICE_EXTENSION *a1,
        const unsigned __int8 *a2,
        unsigned __int16 a3)
{
  unsigned int v4; // ebp
  unsigned int v5; // r11d
  const unsigned __int8 *v6; // r14
  const unsigned __int8 *v7; // rsi
  int v8; // edx
  __int64 v9; // r9
  unsigned int v10; // r11d
  int v11; // r12d
  __int64 v12; // rbx
  int v13; // edx
  int v14; // r8d
  int v15; // edx
  int v16; // r10d
  int v17; // ebx
  char v18; // r15
  __int64 v19; // r9
  __int64 v20; // r8
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  int v27; // eax
  int v28; // r8d
  int v30; // [rsp+20h] [rbp-68h]

  v4 = -1073741436;
  v5 = a2[3 * a3];
  if ( (_BYTE)v5 || *a2 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return v4;
    v28 = *a2;
    v26 = 16;
    v30 = v28;
LABEL_64:
    WPP_SF_dd(v25->AttachedDevice, v26, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v5, v30);
    return v4;
  }
  v6 = &a2[2 * a3];
  v7 = &a2[a3];
  v8 = *v7;
  v9 = *v6;
  if ( (_BYTE)v9 != (_BYTE)v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v9, v8);
    return v4;
  }
  if ( !(_BYTE)v8 || (unsigned __int8)v8 > *(_BYTE *)(*((_QWORD *)a1 + 4) + 4LL) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
        *v7,
        *(unsigned __int8 *)(*((_QWORD *)a1 + 4) + 4LL));
    return v4;
  }
  if ( a3 < (unsigned __int16)(8 * v8 + 1) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a3, v8);
    return v4;
  }
  v10 = 0;
  v11 = *v7;
  while ( 1 )
  {
    if ( (int)v10 >= v11 )
      return 0;
    v12 = (int)v10;
    v13 = v7[8 * v10 + 1];
    v14 = v6[8 * v10 + 1];
    if ( (_BYTE)v13 != (_BYTE)v14 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_DDDD(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
          v10,
          v13,
          v10,
          v14);
      return v4;
    }
    if ( !IsValidInterfaceNumber(a1, v13) )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return v4;
      v27 = v15;
      v26 = 21;
      v30 = v27;
      goto LABEL_64;
    }
    v16 = v7[8 * v12 + 2];
    v17 = v6[8 * v12 + 2];
    if ( !(_BYTE)v16 || !(_BYTE)v17 )
      break;
    if ( (v16 & 6) == 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return v4;
      v26 = 23;
LABEL_42:
      v30 = v16;
      goto LABEL_64;
    }
    if ( (v16 & 6) == 6 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return v4;
      v26 = 24;
      goto LABEL_42;
    }
    v18 = v16 & 1;
    v19 = v16 & 1 | 2LL;
    if ( (v16 & 2) == 0 )
      v19 = v16 & 1;
    v20 = v17 & 1 | 2LL;
    if ( (v17 & 2) == 0 )
      v20 = v17 & 1;
    v21 = v19 | 4;
    if ( (v16 & 4) == 0 )
      v21 = v19;
    v22 = v20 | 4;
    if ( (v17 & 4) == 0 )
      v22 = v20;
    if ( (int)ValidateFlagsFaceAuth(v22, v21) < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v24 = 25;
        goto LABEL_49;
      }
      return v4;
    }
    if ( v18 && (_BYTE)v17 != 1 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v24 = 26;
        goto LABEL_49;
      }
      return v4;
    }
    v10 = v5 + 1;
  }
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v24 = 22;
LABEL_49:
    WPP_SF_DDDD(v23->AttachedDevice, v24, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v5, v16, v5, v17);
  }
  return v4;
}

```

## disassembly

```asm
0x14005a820  push    rbx
0x14005a822  push    rbp
0x14005a823  push    rsi
0x14005a824  push    rdi
0x14005a825  push    r12
0x14005a827  push    r13
0x14005a829  push    r14
0x14005a82b  push    r15
0x14005a82d  sub     rsp, 48h
0x14005a831  movzx   r10d, r8w
0x14005a835  mov     rdi, rcx
0x14005a838  mov     ebp, 0C0000184h
0x14005a83d  lea     eax, [r10+r10*2]
0x14005a841  movzx   r11d, byte ptr [rax+rdx]
0x14005a846  test    r11b, r11b
0x14005a849  jnz     loc_14005AB63
0x14005a84f  cmp     [rdx], r11b
0x14005a852  jnz     loc_14005AB63
0x14005a858  movzx   esi, r8w
0x14005a85c  lea     r14d, [r10+r10]
0x14005a860  add     r14, rdx
0x14005a863  add     rsi, rdx
0x14005a866  movzx   edx, byte ptr [rsi]
0x14005a869  movzx   r9d, byte ptr [r14]
0x14005a86d  cmp     r9b, dl
0x14005a870  jz      short loc_14005A8A3
0x14005a872  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a879  lea     rax, WPP_GLOBAL_Control
0x14005a880  cmp     rcx, rax
0x14005a883  jz      loc_14005AB9D
0x14005a889  cmp     byte ptr [rcx+29h], 2
0x14005a88d  jb      loc_14005AB9D
0x14005a893  mov     eax, edx
0x14005a895  mov     edx, 11h
0x14005a89a  mov     [rsp+88h+var_68], eax
0x14005a89e  jmp     loc_14005AB8D
0x14005a8a3  mov     r13d, 1
0x14005a8a9  cmp     dl, r13b
0x14005a8ac  jb      loc_14005AB32
0x14005a8b2  mov     rax, [rcx+20h]
0x14005a8b6  cmp     dl, [rax+4]
0x14005a8b9  ja      loc_14005AB32
0x14005a8bf  movzx   eax, dx
0x14005a8c2  shl     ax, 3
0x14005a8c6  add     ax, r13w
0x14005a8ca  cmp     r8w, ax
0x14005a8ce  jnb     short loc_14005A903
0x14005a8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a8d7  lea     rax, WPP_GLOBAL_Control
0x14005a8de  cmp     rcx, rax
0x14005a8e1  jz      loc_14005AB9D
0x14005a8e7  cmp     byte ptr [rcx+29h], 2
0x14005a8eb  jb      loc_14005AB9D
0x14005a8f1  mov     eax, edx
0x14005a8f3  mov     r9d, r10d
0x14005a8f6  mov     [rsp+88h+var_68], eax
0x14005a8fa  lea     edx, [r13+12h]
0x14005a8fe  jmp     loc_14005AB8D
0x14005a903  xor     r11d, r11d
0x14005a906  mov     r12d, edx
0x14005a909  cmp     r11d, r12d
0x14005a90c  jge     loc_14005AB2E
0x14005a912  movsxd  rbx, r11d
0x14005a915  movzx   edx, byte ptr [rsi+rbx*8+1]; unsigned __int8
0x14005a91a  movzx   r8d, byte ptr [r14+rbx*8+1]
0x14005a920  cmp     dl, r8b
0x14005a923  jnz     loc_14005AADF
0x14005a929  mov     rcx, rdi; struct _HW_DEVICE_EXTENSION *
0x14005a92c  call    ?IsValidInterfaceNumber@@YAEPEAU_HW_DEVICE_EXTENSION@@E@Z; IsValidInterfaceNumber(_HW_DEVICE_EXTENSION *,uchar)
0x14005a931  test    al, al
0x14005a933  jz      loc_14005AAAE
0x14005a939  movzx   r10d, byte ptr [rsi+rbx*8+2]
0x14005a93f  movzx   ebx, byte ptr [r14+rbx*8+2]
0x14005a945  test    r10b, r10b
0x14005a948  jz      loc_14005AA78
0x14005a94e  test    bl, bl
0x14005a950  jz      loc_14005AA78
0x14005a956  mov     al, r10b
0x14005a959  and     al, 6
0x14005a95b  jz      loc_14005AA50
0x14005a961  cmp     al, 6
0x14005a963  jz      loc_14005AA20
0x14005a969  mov     al, r10b
0x14005a96c  mov     ecx, ebx
0x14005a96e  and     al, r13b
0x14005a971  movzx   r15d, al
0x14005a975  mov     r9d, r15d
0x14005a978  or      r9, 2
0x14005a97c  test    r10b, 2
0x14005a980  cmovz   r9, r15
0x14005a984  and     rcx, r13
0x14005a987  mov     r8, rcx
0x14005a98a  mov     rdx, r9
0x14005a98d  or      r8, 2
0x14005a991  test    bl, 2
0x14005a994  cmovz   r8, rcx
0x14005a998  or      rdx, 4
0x14005a99c  test    r10b, 4
0x14005a9a0  mov     rcx, r8
0x14005a9a3  cmovz   rdx, r9; unsigned __int64
0x14005a9a7  or      rcx, 4
0x14005a9ab  test    bl, 4
0x14005a9ae  cmovz   rcx, r8; unsigned __int64
0x14005a9b2  call    ?ValidateFlagsFaceAuth@@YAJ_K0@Z; ValidateFlagsFaceAuth(unsigned __int64,unsigned __int64)
0x14005a9b7  test    eax, eax
0x14005a9b9  js      short loc_14005A9F8
0x14005a9bb  test    r15b, r15b
0x14005a9be  jz      short loc_14005A9C5
0x14005a9c0  cmp     bl, r13b
0x14005a9c3  jnz     short loc_14005A9CD
0x14005a9c5  add     r11d, r13d
0x14005a9c8  jmp     loc_14005A909
0x14005a9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a9d4  lea     rax, WPP_GLOBAL_Control
0x14005a9db  cmp     rcx, rax
0x14005a9de  jz      loc_14005AB9D
0x14005a9e4  cmp     byte ptr [rcx+29h], 2
0x14005a9e8  jb      loc_14005AB9D
0x14005a9ee  mov     edx, 1Ah
0x14005a9f3  jmp     loc_14005AA9E
0x14005a9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a9ff  lea     rax, WPP_GLOBAL_Control
0x14005aa06  cmp     rcx, rax
0x14005aa09  jz      loc_14005AB9D
0x14005aa0f  cmp     byte ptr [rcx+29h], 2
0x14005aa13  jb      loc_14005AB9D
0x14005aa19  mov     edx, 19h
0x14005aa1e  jmp     short loc_14005AA9E
0x14005aa20  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aa27  lea     rax, WPP_GLOBAL_Control
0x14005aa2e  cmp     rcx, rax
0x14005aa31  jz      loc_14005AB9D
0x14005aa37  cmp     byte ptr [rcx+29h], 2
0x14005aa3b  jb      loc_14005AB9D
0x14005aa41  mov     edx, 18h
0x14005aa46  mov     [rsp+88h+var_68], r10d
0x14005aa4b  jmp     loc_14005AB8A
0x14005aa50  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aa57  lea     rax, WPP_GLOBAL_Control
0x14005aa5e  cmp     rcx, rax
0x14005aa61  jz      loc_14005AB9D
0x14005aa67  cmp     byte ptr [rcx+29h], 2
0x14005aa6b  jb      loc_14005AB9D
0x14005aa71  mov     edx, 17h
0x14005aa76  jmp     short loc_14005AA46
0x14005aa78  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aa7f  lea     rax, WPP_GLOBAL_Control
0x14005aa86  cmp     rcx, rax
0x14005aa89  jz      loc_14005AB9D
0x14005aa8f  cmp     byte ptr [rcx+29h], 2
0x14005aa93  jb      loc_14005AB9D
0x14005aa99  mov     edx, 16h
0x14005aa9e  mov     [rsp+88h+var_58], ebx
0x14005aaa2  mov     [rsp+88h+var_60], r11d
0x14005aaa7  mov     [rsp+88h+var_68], r10d
0x14005aaac  jmp     short loc_14005AB19
0x14005aaae  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aab5  lea     rax, WPP_GLOBAL_Control
0x14005aabc  cmp     rcx, rax
0x14005aabf  jz      loc_14005AB9D
0x14005aac5  cmp     byte ptr [rcx+29h], 2
0x14005aac9  jb      loc_14005AB9D
0x14005aacf  mov     eax, edx
0x14005aad1  mov     edx, 15h
0x14005aad6  mov     [rsp+88h+var_68], eax
0x14005aada  jmp     loc_14005AB8A
0x14005aadf  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aae6  lea     rax, WPP_GLOBAL_Control
0x14005aaed  cmp     rcx, rax
0x14005aaf0  jz      loc_14005AB9D
0x14005aaf6  cmp     byte ptr [rcx+29h], 2
0x14005aafa  jb      loc_14005AB9D
0x14005ab00  mov     eax, r8d
0x14005ab03  mov     r8d, edx
0x14005ab06  mov     [rsp+88h+var_58], eax
0x14005ab0a  mov     edx, 14h
0x14005ab0f  mov     [rsp+88h+var_60], r11d
0x14005ab14  mov     [rsp+88h+var_68], r8d
0x14005ab19  mov     rcx, [rcx+18h]
0x14005ab1d  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005ab24  mov     r9d, r11d
0x14005ab27  call    WPP_SF_DDDD
0x14005ab2c  jmp     short loc_14005AB9D
0x14005ab2e  xor     ebp, ebp
0x14005ab30  jmp     short loc_14005AB9D
0x14005ab32  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab39  lea     rax, WPP_GLOBAL_Control
0x14005ab40  cmp     rcx, rax
0x14005ab43  jz      short loc_14005AB9D
0x14005ab45  cmp     byte ptr [rcx+29h], 2
0x14005ab49  jb      short loc_14005AB9D
0x14005ab4b  mov     rax, [rdi+20h]
0x14005ab4f  mov     r9d, edx
0x14005ab52  mov     edx, 12h
0x14005ab57  movzx   r8d, byte ptr [rax+4]
0x14005ab5c  mov     [rsp+88h+var_68], r8d
0x14005ab61  jmp     short loc_14005AB8D
0x14005ab63  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab6a  lea     rax, WPP_GLOBAL_Control
0x14005ab71  cmp     rcx, rax
0x14005ab74  jz      short loc_14005AB9D
0x14005ab76  cmp     byte ptr [rcx+29h], 2
0x14005ab7a  jb      short loc_14005AB9D
0x14005ab7c  movzx   r8d, byte ptr [rdx]
0x14005ab80  mov     edx, 10h
0x14005ab85  mov     [rsp+88h+var_68], r8d
0x14005ab8a  mov     r9d, r11d
0x14005ab8d  mov     rcx, [rcx+18h]
0x14005ab91  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005ab98  call    WPP_SF_dd
0x14005ab9d  mov     eax, ebp
0x14005ab9f  add     rsp, 48h
0x14005aba3  pop     r15
0x14005aba5  pop     r14
0x14005aba7  pop     r13
0x14005aba9  pop     r12
0x14005abab  pop     rdi
0x14005abac  pop     rsi
0x14005abad  pop     rbp
0x14005abae  pop     rbx
0x14005abaf  retn
```
