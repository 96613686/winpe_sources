# CTextNormMultiResult::GetTopResults(long,ushort * * *,long *)

- ea: `0x18000cd70`
- end: `0x18000cef7`
- name: `?GetTopResults@CTextNormMultiResult@@UEAAJJPEAPEAPEAGPEAJ@Z`
- size: `391`
- prototype: `__int64 __fastcall(CTextNormMultiResult *__hidden this, int, unsigned __int16 ***, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800031c8`
- `0x180009470`
- `0x18000a614`
- `0x18000cd70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTextNormMultiResult::GetTopResults(
        CTextNormMultiResult *this,
        __int64 a2,
        unsigned __int16 ***a3,
        int *a4)
{
  int v5; // ebx
  int v6; // r12d
  __int64 v7; // rsi
  SIZE_T v8; // rcx
  _QWORD *v9; // rdi
  _QWORD *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // rax
  unsigned __int16 **v14; // rax
  unsigned __int16 **v15; // r14
  int v16; // ebp
  unsigned __int16 *v17; // rsi
  __int64 v18; // rax
  _WORD *v19; // rdx
  __int64 v20; // r15
  _QWORD v22[2]; // [rsp+20h] [rbp-88h] BYREF
  int v23; // [rsp+30h] [rbp-78h]
  __int64 v24; // [rsp+38h] [rbp-70h]
  __int64 v25; // [rsp+40h] [rbp-68h]
  int v26; // [rsp+48h] [rbp-60h]
  int v27; // [rsp+54h] [rbp-54h]

  v23 = 0;
  v24 = 0;
  v22[1] = 0;
  v22[0] = 0;
  v25 = 0;
  v26 = 10;
  v27 = 0;
  if ( (int)a2 <= 0 || !a3 || !a4 )
  {
    v5 = -2147024809;
    goto LABEL_28;
  }
  v5 = CTextNormMultiResult::ComputeTopResults(this, a2, v22, 0);
  if ( v5 >= 0 )
  {
    v6 = v23;
    if ( v23 < 1 )
    {
      v5 = -2147217404;
      goto LABEL_28;
    }
    v7 = v23;
    v8 = v7 * 8;
    v9 = (_QWORD *)v22[0];
    v10 = (_QWORD *)v22[0];
    if ( v22[0] )
    {
      while ( 1 )
      {
        v11 = v10[2];
        v10 = (_QWORD *)*v10;
        if ( !*(_QWORD *)v11 )
          goto LABEL_13;
        v12 = *(_QWORD *)(*(_QWORD *)v11 + 64LL);
        if ( v12 )
          break;
LABEL_14:
        if ( !v10 )
          goto LABEL_15;
      }
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)(v12 + 2 * v13) );
      v8 += 2 * v13;
LABEL_13:
      v8 += 2LL;
      goto LABEL_14;
    }
LABEL_15:
    v14 = (unsigned __int16 **)CoTaskMemAlloc(v8);
    v15 = v14;
    if ( v14 )
    {
      v16 = 0;
      v17 = (unsigned __int16 *)&v14[v7];
      while ( v9 )
      {
        v18 = v9[2];
        v9 = (_QWORD *)*v9;
        if ( *(_QWORD *)v18 )
        {
          v19 = *(_WORD **)(*(_QWORD *)v18 + 64LL);
          if ( v19 )
          {
            v20 = -1;
            do
              ++v20;
            while ( v19[v20] );
            v15[v16] = v17;
            memcpy_0(v17, v19, 2 * v20 + 2);
            v17 += v20 + 1;
          }
        }
        else
        {
          v15[v16] = v17;
          *v17++ = 0;
        }
        ++v16;
      }
      *a3 = v15;
      *a4 = v6;
    }
    else
    {
      v5 = -2147024882;
    }
  }
LABEL_28:
  CTnMultiResStringPackage::~CTnMultiResStringPackage((CTnMultiResStringPackage *)v22);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000cd70  mov     r11, rsp
0x18000cd73  mov     [r11+18h], r8
0x18000cd77  push    rbx
0x18000cd78  push    rbp
0x18000cd79  push    rsi
0x18000cd7a  push    rdi
0x18000cd7b  push    r12
0x18000cd7d  push    r13
0x18000cd7f  push    r14
0x18000cd81  push    r15
0x18000cd83  sub     rsp, 68h
0x18000cd87  mov     r13, r9
0x18000cd8a  mov     rax, r8
0x18000cd8d  xor     r15d, r15d
0x18000cd90  mov     [r11-78h], r15d
0x18000cd94  mov     [r11-70h], r15
0x18000cd98  mov     [r11-80h], r15
0x18000cd9c  mov     [rsp+0A8h+var_88], r15
0x18000cda1  mov     [r11-68h], r15
0x18000cda5  mov     [rsp+0A8h+var_60], 0Ah
0x18000cdad  mov     [r11-54h], r15d
0x18000cdb1  test    edx, edx
0x18000cdb3  jle     loc_18000CED5
0x18000cdb9  test    rax, rax
0x18000cdbc  jz      loc_18000CED5
0x18000cdc2  test    r9, r9
0x18000cdc5  jz      loc_18000CED5
0x18000cdcb  xor     r9d, r9d
0x18000cdce  lea     r8, [rsp+0A8h+var_88]
0x18000cdd3  call    ?ComputeTopResults@CTextNormMultiResult@@AEAAJJPEAVCTnMultiResStringPackage@@PEAV?$CSPList@PEAUIParseTreeNode@@PEAU1@@@@Z; CTextNormMultiResult::ComputeTopResults(long,CTnMultiResStringPackage *,CSPList<IParseTreeNode *,IParseTreeNode *> *)
0x18000cdd8  mov     ebx, eax
0x18000cdda  test    eax, eax
0x18000cddc  js      loc_18000CEDA
0x18000cde2  movsxd  r12, [rsp+0A8h+var_78]
0x18000cde7  cmp     r12d, 1
0x18000cdeb  jge     short loc_18000CDF7
0x18000cded  mov     ebx, 80041004h
0x18000cdf2  jmp     loc_18000CEDA
0x18000cdf7  lea     rsi, ds:0[r12*8]
0x18000cdff  mov     rcx, rsi
0x18000ce02  mov     rdi, [rsp+0A8h+var_88]
0x18000ce07  mov     rdx, rdi
0x18000ce0a  test    rdi, rdi
0x18000ce0d  jz      short loc_18000CE42
0x18000ce0f  mov     rax, [rdx+10h]
0x18000ce13  mov     rdx, [rdx]
0x18000ce16  mov     r8, [rax]
0x18000ce19  test    r8, r8
0x18000ce1c  jz      short loc_18000CE39
0x18000ce1e  mov     r9, [r8+40h]
0x18000ce22  test    r9, r9
0x18000ce25  jz      short loc_18000CE3D
0x18000ce27  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ce2b  inc     rax
0x18000ce2e  cmp     [r9+rax*2], r15w
0x18000ce33  jnz     short loc_18000CE2B
0x18000ce35  lea     rcx, [rcx+rax*2]
0x18000ce39  add     rcx, 2; cb
0x18000ce3d  test    rdx, rdx
0x18000ce40  jnz     short loc_18000CE0F
0x18000ce42  call    cs:__imp_CoTaskMemAlloc
0x18000ce48  mov     r14, rax
0x18000ce4b  test    rax, rax
0x18000ce4e  jnz     short loc_18000CE5A
0x18000ce50  mov     ebx, 8007000Eh
0x18000ce55  jmp     loc_18000CEDA
0x18000ce5a  mov     ebp, r15d
0x18000ce5d  add     rsi, r14
0x18000ce60  jmp     short loc_18000CEBF
0x18000ce62  mov     rax, [rdi+10h]
0x18000ce66  mov     rdi, [rdi]
0x18000ce69  mov     rcx, [rax]
0x18000ce6c  test    rcx, rcx
0x18000ce6f  jz      short loc_18000CEAE
0x18000ce71  mov     rdx, [rcx+40h]; Src
0x18000ce75  test    rdx, rdx
0x18000ce78  jz      short loc_18000CEBD
0x18000ce7a  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000ce7e  xor     eax, eax
0x18000ce80  inc     r15
0x18000ce83  cmp     [rdx+r15*2], ax
0x18000ce88  jnz     short loc_18000CE80
0x18000ce8a  movsxd  rax, ebp
0x18000ce8d  mov     [r14+rax*8], rsi
0x18000ce91  lea     r8, ds:2[r15*2]; Size
0x18000ce99  mov     rcx, rsi; void *
0x18000ce9c  call    memcpy_0
0x18000cea1  lea     rsi, [rsi+r15*2]
0x18000cea5  add     rsi, 2
0x18000cea9  xor     r15d, r15d
0x18000ceac  jmp     short loc_18000CEBD
0x18000ceae  movsxd  rax, ebp
0x18000ceb1  mov     [r14+rax*8], rsi
0x18000ceb5  mov     [rsi], r15w
0x18000ceb9  add     rsi, 2
0x18000cebd  inc     ebp
0x18000cebf  test    rdi, rdi
0x18000cec2  jnz     short loc_18000CE62
0x18000cec4  mov     rax, [rsp+0A8h+arg_10]
0x18000cecc  mov     [rax], r14
0x18000cecf  mov     [r13+0], r12d
0x18000ced3  jmp     short loc_18000CEDA
0x18000ced5  mov     ebx, 80070057h
0x18000ceda  lea     rcx, [rsp+0A8h+var_88]; this
0x18000cedf  call    ??1CTnMultiResStringPackage@@QEAA@XZ; CTnMultiResStringPackage::~CTnMultiResStringPackage(void)
0x18000cee4  mov     eax, ebx
0x18000cee6  add     rsp, 68h
0x18000ceea  pop     r15
0x18000ceec  pop     r14
0x18000ceee  pop     r13
0x18000cef0  pop     r12
0x18000cef2  pop     rdi
0x18000cef3  pop     rsi
0x18000cef4  pop     rbp
0x18000cef5  pop     rbx
0x18000cef6  retn
```
