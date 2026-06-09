# SrSmapipDeleteReplicationGroupSetReturn

- ea: `0x18000cb74`
- end: `0x18000cd99`
- name: `SrSmapipDeleteReplicationGroupSetReturn`
- size: `549`
- prototype: `__int64 __fastcall(enum _MI_Result, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180009844`

## callees

- `0x1800014e0`
- `0x180001e08`
- `0x180005cac`
- `0x180006778`
- `0x1800067a0`
- `0x18000cb74`
- `0x18001bedc`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall SrSmapipDeleteReplicationGroupSetReturn(enum _MI_Result a1, struct CWMIContext *a2)
{
  _QWORD *v4; // rbx
  enum _MI_Result v5; // edi
  char v6; // r14
  __int64 v7; // rcx
  enum _MI_Result v8; // eax
  int v9; // esi
  __int64 v10; // rcx
  __int64 v11; // rcx
  MI_Instance *p_self; // [rsp+30h] [rbp-D0h] BYREF
  MI_Instance v14; // [rsp+40h] [rbp-C0h] BYREF
  enum _MI_Result v15; // [rsp+80h] [rbp-80h]
  char v16; // [rsp+84h] [rbp-7Ch]
  MI_Instance self; // [rsp+A0h] [rbp-60h] BYREF

  v4 = WPP_GLOBAL_Control;
  v5 = MI_RESULT_INVALID_PARAMETER;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  self.ft = 0;
  v6 = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  v14.ft = 0;
  memset_0(&v14.classDecl, 0, 0x50u);
  v7 = *((_QWORD *)a2 + 7);
  if ( !v7 || !*(_QWORD *)v7 )
  {
    v9 = 4;
    v8 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_24;
  }
  v8 = (*(unsigned int (__fastcall **)(__int64, __int64 *, MI_Instance *))(*(_QWORD *)v7 + 32LL))(
         v7,
         &WSP_ReplicationGroup_DeleteObject_rtti,
         &v14);
  v9 = v8;
  if ( v8 )
    goto LABEL_22;
  v10 = *((_QWORD *)a2 + 7);
  if ( v10 && *(_QWORD *)v10 )
  {
    v8 = (*(unsigned int (__fastcall **)(__int64, __int64 *, MI_Instance *))(*(_QWORD *)v10 + 24LL))(
           v10,
           &MSFT_StorageExtendedStatus_rtti,
           &self);
    if ( v8 )
      goto LABEL_22;
    v8 = SrSmapiPopulateStorageExtendedStatus((struct _MSFT_StorageExtendedStatus *)&self, a1, a2);
    if ( v8 == MI_RESULT_OK )
    {
      p_self = &self;
      v8 = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, MI_Instance **, _QWORD, int))v14.ft->SetElementAt)(
             &v14,
             (unsigned int)(v9 + 1),
             &p_self,
             (unsigned int)(v9 + 15),
             v9);
      v6 = 1;
      if ( v8 == MI_RESULT_OK )
      {
        v15 = a1;
        v16 = 1;
        goto LABEL_15;
      }
LABEL_22:
      v4 = WPP_GLOBAL_Control;
LABEL_24:
      v5 = v8;
      goto LABEL_25;
    }
    v6 = 1;
  }
  else
  {
    v8 = MI_RESULT_INVALID_PARAMETER;
  }
LABEL_15:
  if ( v8 )
    goto LABEL_22;
  v11 = *((_QWORD *)a2 + 7);
  if ( v11 && *(_QWORD *)v11 )
    v5 = (*(unsigned int (__fastcall **)(__int64, MI_Instance *))(*(_QWORD *)v11 + 8LL))(v11, &v14);
  v4 = WPP_GLOBAL_Control;
  if ( v5 == MI_RESULT_OK )
    v5 = a1;
LABEL_25:
  if ( v6 )
  {
    MI_Instance_Destruct(&self);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !v9 )
  {
    MI_Instance_Destruct(&v14);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
    WPP_SF_d(v4[2], 25, WPP_97259de4980931de249eb41af43a46d5_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000cb74  mov     [rsp-8+arg_10], rbx
0x18000cb79  mov     [rsp-8+arg_18], rsi
0x18000cb7e  push    rbp
0x18000cb7f  push    rdi
0x18000cb80  push    r12
0x18000cb82  push    r14
0x18000cb84  push    r15
0x18000cb86  lea     rbp, [rsp-0C0h]
0x18000cb8e  sub     rsp, 1C0h
0x18000cb95  mov     rax, cs:__security_cookie
0x18000cb9c  xor     rax, rsp
0x18000cb9f  mov     [rbp+0E0h+var_30], rax
0x18000cba6  mov     r15, rdx
0x18000cba9  mov     r12d, ecx
0x18000cbac  mov     rbx, cs:WPP_GLOBAL_Control
0x18000cbb3  lea     rax, WPP_GLOBAL_Control
0x18000cbba  mov     edi, 4
0x18000cbbf  cmp     rbx, rax
0x18000cbc2  jz      short loc_18000CBE4
0x18000cbc4  test    [rbx+1Ch], dil
0x18000cbc8  jz      short loc_18000CBE4
0x18000cbca  mov     rcx, [rbx+10h]
0x18000cbce  lea     edx, [rdi+14h]
0x18000cbd1  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000cbd8  call    WPP_SF_
0x18000cbdd  mov     rbx, cs:WPP_GLOBAL_Control
0x18000cbe4  xor     edx, edx; Val
0x18000cbe6  mov     [rbp+0E0h+self.ft], 0
0x18000cbee  mov     r8d, 108h; Size
0x18000cbf4  lea     rcx, [rbp+0E0h+self.classDecl]; void *
0x18000cbf8  xor     r14b, r14b
0x18000cbfb  call    memset_0
0x18000cc00  xor     edx, edx; Val
0x18000cc02  mov     [rsp+1E0h+var_1A0.ft], 0
0x18000cc0b  lea     rcx, [rsp+1E0h+var_1A0.classDecl]; void *
0x18000cc10  lea     r8d, [rdx+50h]; Size
0x18000cc14  call    memset_0
0x18000cc19  mov     rcx, [r15+38h]
0x18000cc1d  test    rcx, rcx
0x18000cc20  jz      loc_18000CD12
0x18000cc26  mov     rax, [rcx]
0x18000cc29  test    rax, rax
0x18000cc2c  jz      loc_18000CD12
0x18000cc32  mov     rax, [rax+20h]
0x18000cc36  lea     r8, [rsp+1E0h+var_1A0]
0x18000cc3b  lea     rdx, WSP_ReplicationGroup_DeleteObject_rtti
0x18000cc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc47  mov     esi, eax
0x18000cc49  test    eax, eax
0x18000cc4b  jnz     loc_18000CD09
0x18000cc51  mov     rcx, [r15+38h]
0x18000cc55  test    rcx, rcx
0x18000cc58  jz      short loc_18000CCD3
0x18000cc5a  mov     rax, [rcx]
0x18000cc5d  test    rax, rax
0x18000cc60  jz      short loc_18000CCD3
0x18000cc62  mov     rax, [rax+18h]
0x18000cc66  lea     r8, [rbp+0E0h+self]
0x18000cc6a  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x18000cc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc76  test    eax, eax
0x18000cc78  jnz     loc_18000CD09
0x18000cc7e  mov     r8, r15; struct CWMIContext *
0x18000cc81  lea     rcx, [rbp+0E0h+self]; struct _MSFT_StorageExtendedStatus *
0x18000cc85  mov     edx, r12d; enum _MI_Result
0x18000cc88  call    ?SrSmapiPopulateStorageExtendedStatus@@YA?AW4_MI_Result@@PEAU_MSFT_StorageExtendedStatus@@W41@AEAVCWMIContext@@@Z; SrSmapiPopulateStorageExtendedStatus(_MSFT_StorageExtendedStatus *,_MI_Result,CWMIContext &)
0x18000cc8d  test    eax, eax
0x18000cc8f  jnz     short loc_18000CCCE
0x18000cc91  lea     rax, [rbp+0E0h+self]
0x18000cc95  mov     [rsp+1E0h+var_1C0], esi
0x18000cc99  mov     [rsp+1E0h+var_1B0], rax
0x18000cc9e  lea     r9d, [rsi+0Fh]
0x18000cca2  mov     rax, [rsp+1E0h+var_1A0.ft]
0x18000cca7  lea     r8, [rsp+1E0h+var_1B0]
0x18000ccac  lea     edx, [rsi+1]
0x18000ccaf  lea     rcx, [rsp+1E0h+var_1A0]
0x18000ccb4  mov     rax, [rax+50h]
0x18000ccb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccbd  mov     r14b, 1
0x18000ccc0  test    eax, eax
0x18000ccc2  jnz     short loc_18000CD09
0x18000ccc4  mov     [rbp+0E0h+var_160], r12d
0x18000ccc8  mov     [rbp+0E0h+var_15C], r14b
0x18000cccc  jmp     short loc_18000CCD5
0x18000ccce  mov     r14b, 1
0x18000ccd1  jmp     short loc_18000CCD5
0x18000ccd3  mov     eax, edi
0x18000ccd5  test    eax, eax
0x18000ccd7  jnz     short loc_18000CD09
0x18000ccd9  mov     rcx, [r15+38h]
0x18000ccdd  test    rcx, rcx
0x18000cce0  jz      short loc_18000CCFA
0x18000cce2  mov     rax, [rcx]
0x18000cce5  test    rax, rax
0x18000cce8  jz      short loc_18000CCFA
0x18000ccea  mov     rax, [rax+8]
0x18000ccee  lea     rdx, [rsp+1E0h+var_1A0]
0x18000ccf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccf8  mov     edi, eax
0x18000ccfa  mov     rbx, cs:WPP_GLOBAL_Control
0x18000cd01  test    edi, edi
0x18000cd03  cmovz   edi, r12d
0x18000cd07  jmp     short loc_18000CD18
0x18000cd09  mov     rbx, cs:WPP_GLOBAL_Control
0x18000cd10  jmp     short loc_18000CD16
0x18000cd12  mov     esi, edi
0x18000cd14  mov     eax, edi
0x18000cd16  mov     edi, eax
0x18000cd18  test    r14b, r14b
0x18000cd1b  jz      short loc_18000CD2D
0x18000cd1d  lea     rcx, [rbp+0E0h+self]; self
0x18000cd21  call    MI_Instance_Destruct
0x18000cd26  mov     rbx, cs:WPP_GLOBAL_Control
0x18000cd2d  test    esi, esi
0x18000cd2f  jnz     short loc_18000CD42
0x18000cd31  lea     rcx, [rsp+1E0h+var_1A0]; self
0x18000cd36  call    MI_Instance_Destruct
0x18000cd3b  mov     rbx, cs:WPP_GLOBAL_Control
0x18000cd42  lea     rax, WPP_GLOBAL_Control
0x18000cd49  cmp     rbx, rax
0x18000cd4c  jz      short loc_18000CD6C
0x18000cd4e  test    byte ptr [rbx+1Ch], 1
0x18000cd52  jz      short loc_18000CD6C
0x18000cd54  mov     rcx, [rbx+10h]
0x18000cd58  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000cd5f  mov     edx, 19h
0x18000cd64  mov     r9d, edi
0x18000cd67  call    WPP_SF_d
0x18000cd6c  mov     eax, edi
0x18000cd6e  mov     rcx, [rbp+0E0h+var_30]
0x18000cd75  xor     rcx, rsp; StackCookie
0x18000cd78  call    __security_check_cookie
0x18000cd7d  lea     r11, [rsp+1E0h+var_20]
0x18000cd85  mov     rbx, [r11+40h]
0x18000cd89  mov     rsi, [r11+48h]
0x18000cd8d  mov     rsp, r11
0x18000cd90  pop     r15
0x18000cd92  pop     r14
0x18000cd94  pop     r12
0x18000cd96  pop     rdi
0x18000cd97  pop     rbp
0x18000cd98  retn
```
