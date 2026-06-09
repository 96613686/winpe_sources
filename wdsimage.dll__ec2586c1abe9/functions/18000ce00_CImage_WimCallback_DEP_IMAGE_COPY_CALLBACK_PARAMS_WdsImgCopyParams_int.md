# CImage::WimCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)

- ea: `0x18000ce00`
- end: `0x18000cf7a`
- name: `?WimCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z`
- size: `378`
- prototype: `__int64 __fastcall(CImage *__hidden this, struct _DEP_IMAGE_COPY_CALLBACK_PARAMS *, struct WdsImgCopyParams *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d210`

## callees

- `0x18000ce00`
- `0x18000d5b0`

## pseudocode

```c
__int64 __fastcall CImage::WimCallback(
        CImage *this,
        struct _DEP_IMAGE_COPY_CALLBACK_PARAMS *a2,
        struct WdsImgCopyParams *a3,
        int *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rcx
  char *v9; // rdx
  __int64 v10; // r8
  signed __int64 v11; // r9
  __int16 v12; // ax
  char *v13; // rax
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int16 v18; // ax
  char *v19; // rax

  v7 = 0;
  if ( !*((_DWORD *)a3 + 8)
    || (v7 = -2147023673, (int)ElValidateHr_5(2147943623LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3190) >= 0) )
  {
    if ( *((_DWORD *)a3 + 14) && (*(_BYTE *)a2 & 8) != 0 )
    {
      v8 = *((_QWORD *)a2 + 5);
      v9 = (char *)*((_QWORD *)a2 + 4);
      if ( (unsigned __int64)(v8 - 1) > 0x7FFFFFFE )
      {
        v7 = -2147024809;
        if ( v8 )
          *(_WORD *)v9 = 0;
      }
      else
      {
        v10 = 2147483646 - v8;
        v11 = (char *)L"Res.RWM" - v9;
        do
        {
          if ( !(v10 + v8) )
            break;
          v12 = *(_WORD *)&v9[v11];
          if ( !v12 )
            break;
          *(_WORD *)v9 = v12;
          v9 += 2;
          --v8;
        }
        while ( v8 );
        v13 = v9 - 2;
        if ( v8 )
          v13 = v9;
        v7 = v8 == 0 ? 0x8007007A : 0;
        *(_WORD *)v13 = 0;
      }
      v14 = 3203;
    }
    else
    {
      if ( (*(_BYTE *)a2 & 1) == 0 )
      {
LABEL_29:
        *a4 = 0;
        return v7;
      }
      v15 = *((_QWORD *)a2 + 5);
      v9 = (char *)*((_QWORD *)a2 + 4);
      if ( (unsigned __int64)(v15 - 1) > 0x7FFFFFFE )
      {
        v7 = -2147024809;
        if ( v15 )
          *(_WORD *)v9 = 0;
      }
      else
      {
        v16 = 2147483646 - v15;
        v17 = *((_QWORD *)a3 + 2) - (_QWORD)v9;
        do
        {
          if ( !(v16 + v15) )
            break;
          v18 = *(_WORD *)&v9[v17];
          if ( !v18 )
            break;
          *(_WORD *)v9 = v18;
          v9 += 2;
          --v15;
        }
        while ( v15 );
        v19 = v9 - 2;
        if ( v15 )
          v19 = v9;
        v7 = v15 == 0 ? 0x8007007A : 0;
        *(_WORD *)v19 = 0;
      }
      v14 = 3211;
    }
    if ( (int)ElValidateHr_5(v7, v9, "base\\eco\\wds\\wdsimage\\src\\image.cpp", v14) >= 0 )
      goto LABEL_29;
  }
  return v7;
}

```

## disassembly

```asm
0x18000ce00  mov     rax, rsp
0x18000ce03  mov     [rax+8], rbx
0x18000ce07  mov     [rax+10h], rbp
0x18000ce0b  mov     [rax+18h], rsi
0x18000ce0f  mov     [rax+20h], rdi
0x18000ce13  push    r14
0x18000ce15  sub     rsp, 20h
0x18000ce19  xor     ebp, ebp
0x18000ce1b  mov     r14, r9
0x18000ce1e  mov     rsi, r8
0x18000ce21  mov     rdi, rdx
0x18000ce24  mov     ebx, ebp
0x18000ce26  cmp     [r8+20h], ebp
0x18000ce2a  jz      short loc_18000CE4D
0x18000ce2c  mov     ebx, 800704C7h
0x18000ce31  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000ce38  mov     ecx, ebx
0x18000ce3a  mov     r9d, 0C76h
0x18000ce40  call    ElValidateHr_5
0x18000ce45  test    eax, eax
0x18000ce47  js      loc_18000CF5C
0x18000ce4d  cmp     [rsi+38h], ebp
0x18000ce50  jz      short loc_18000CECD
0x18000ce52  test    byte ptr [rdi], 8
0x18000ce55  jz      short loc_18000CECD
0x18000ce57  mov     rcx, [rdi+28h]
0x18000ce5b  mov     r8d, 7FFFFFFEh
0x18000ce61  mov     rdx, [rdi+20h]
0x18000ce65  lea     rax, [rcx-1]
0x18000ce69  cmp     rax, r8
0x18000ce6c  ja      short loc_18000CEB8
0x18000ce6e  sub     r8, rcx
0x18000ce71  lea     r9, aResRwm; "Res.RWM"
0x18000ce78  sub     r9, rdx
0x18000ce7b  lea     rax, [r8+rcx]
0x18000ce7f  test    rax, rax
0x18000ce82  jz      short loc_18000CE9B
0x18000ce84  movzx   eax, word ptr [r9+rdx]
0x18000ce89  test    ax, ax
0x18000ce8c  jz      short loc_18000CE9B
0x18000ce8e  mov     [rdx], ax
0x18000ce91  add     rdx, 2
0x18000ce95  sub     rcx, 1
0x18000ce99  jnz     short loc_18000CE7B
0x18000ce9b  test    rcx, rcx
0x18000ce9e  lea     rax, [rdx-2]
0x18000cea2  cmovnz  rax, rdx
0x18000cea6  neg     rcx
0x18000cea9  sbb     ebx, ebx
0x18000ceab  not     ebx
0x18000cead  and     ebx, 8007007Ah
0x18000ceb3  mov     [rax], bp
0x18000ceb6  jmp     short loc_18000CEC5
0x18000ceb8  mov     ebx, 80070057h
0x18000cebd  test    rcx, rcx
0x18000cec0  jz      short loc_18000CEC5
0x18000cec2  mov     [rdx], bp
0x18000cec5  mov     r9d, 0C83h
0x18000cecb  jmp     short loc_18000CF47
0x18000cecd  test    byte ptr [rdi], 1
0x18000ced0  jz      loc_18000CF59
0x18000ced6  mov     rcx, [rdi+28h]
0x18000ceda  mov     r8d, 7FFFFFFEh
0x18000cee0  mov     r9, [rsi+10h]
0x18000cee4  mov     rdx, [rdi+20h]
0x18000cee8  lea     rax, [rcx-1]
0x18000ceec  cmp     rax, r8
0x18000ceef  ja      short loc_18000CF34
0x18000cef1  sub     r8, rcx
0x18000cef4  sub     r9, rdx
0x18000cef7  lea     rax, [r8+rcx]
0x18000cefb  test    rax, rax
0x18000cefe  jz      short loc_18000CF17
0x18000cf00  movzx   eax, word ptr [r9+rdx]
0x18000cf05  test    ax, ax
0x18000cf08  jz      short loc_18000CF17
0x18000cf0a  mov     [rdx], ax
0x18000cf0d  add     rdx, 2
0x18000cf11  sub     rcx, 1
0x18000cf15  jnz     short loc_18000CEF7
0x18000cf17  test    rcx, rcx
0x18000cf1a  lea     rax, [rdx-2]
0x18000cf1e  cmovnz  rax, rdx
0x18000cf22  neg     rcx
0x18000cf25  sbb     ebx, ebx
0x18000cf27  not     ebx
0x18000cf29  and     ebx, 8007007Ah
0x18000cf2f  mov     [rax], bp
0x18000cf32  jmp     short loc_18000CF41
0x18000cf34  mov     ebx, 80070057h
0x18000cf39  test    rcx, rcx
0x18000cf3c  jz      short loc_18000CF41
0x18000cf3e  mov     [rdx], bp
0x18000cf41  mov     r9d, 0C8Bh
0x18000cf47  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000cf4e  mov     ecx, ebx
0x18000cf50  call    ElValidateHr_5
0x18000cf55  test    eax, eax
0x18000cf57  js      short loc_18000CF5C
0x18000cf59  mov     [r14], ebp
0x18000cf5c  mov     rbp, [rsp+28h+arg_8]
0x18000cf61  mov     eax, ebx
0x18000cf63  mov     rbx, [rsp+28h+arg_0]
0x18000cf68  mov     rsi, [rsp+28h+arg_10]
0x18000cf6d  mov     rdi, [rsp+28h+arg_18]
0x18000cf72  add     rsp, 20h
0x18000cf76  pop     r14
0x18000cf78  retn
```
