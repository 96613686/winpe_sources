# SrSmapipDeleteReplicationGroupSetReturn

- ea: `0x18000cb64`
- end: `0x18000cd1b`
- name: `SrSmapipDeleteReplicationGroupSetReturn`
- size: `439`
- prototype: `__int64 __fastcall(enum _MI_Result, struct CWMIContext *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180009994`

## callees

- `0x1800014e0`
- `0x180001e38`
- `0x1800029e4`
- `0x180005cec`
- `0x1800067cc`
- `0x1800067fc`
- `0x180009028`
- `0x18000cb64`
- `0x18001bf54`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall SrSmapipDeleteReplicationGroupSetReturn(enum _MI_Result a1, MI_Context **a2)
{
  MI_Result v4; // r15d
  enum _MI_Result v5; // ebx
  char v6; // di
  MI_Instance *p_self; // [rsp+30h] [rbp-D0h] BYREF
  MI_Instance instance; // [rsp+40h] [rbp-C0h] BYREF
  enum _MI_Result v10; // [rsp+80h] [rbp-80h]
  char v11; // [rsp+84h] [rbp-7Ch]
  MI_Instance self; // [rsp+A0h] [rbp-60h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_97259de4980931de249eb41af43a46d5_Traceguids);
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0x108u);
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x50u);
  v4 = MI_Context_ConstructParameters(a2[7], &WSP_ReplicationGroup_DeleteObject_rtti, &instance);
  if ( v4 )
  {
    v5 = v4;
    goto LABEL_10;
  }
  v5 = MI_Context_ConstructInstance(a2[7], &MSFT_StorageExtendedStatus_rtti, &self);
  if ( v5 )
  {
LABEL_10:
    v6 = 0;
    goto LABEL_11;
  }
  v5 = SrSmapiPopulateStorageExtendedStatus((struct _MSFT_StorageExtendedStatus *)&self, a1, (struct CWMIContext *)a2);
  v6 = 1;
  if ( v5 == MI_RESULT_OK )
  {
    p_self = &self;
    v5 = ((unsigned int (__fastcall *)(MI_Instance *, __int64, MI_Instance **, _QWORD, _DWORD))instance.ft->SetElementAt)(
           &instance,
           1,
           &p_self,
           (unsigned int)(v4 + 15),
           0);
    if ( v5 == MI_RESULT_OK )
    {
      v10 = a1;
      v11 = 1;
    }
  }
LABEL_11:
  if ( v5 == MI_RESULT_OK )
  {
    v5 = MI_Instance_Destruct((MI_Instance *)a2[7]);
    if ( v5 == MI_RESULT_OK )
      v5 = a1;
  }
  if ( v6 )
    MI_Instance_Destruct(&self);
  if ( v4 == MI_RESULT_OK )
    MI_Instance_Destruct(&instance);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_97259de4980931de249eb41af43a46d5_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000cb64  mov     [rsp-8+arg_10], rbx
0x18000cb69  mov     [rsp-8+arg_18], rsi
0x18000cb6e  push    rbp
0x18000cb6f  push    rdi
0x18000cb70  push    r13
0x18000cb72  push    r14
0x18000cb74  push    r15
0x18000cb76  lea     rbp, [rsp-0C0h]
0x18000cb7e  sub     rsp, 1C0h
0x18000cb85  mov     rax, cs:__security_cookie
0x18000cb8c  xor     rax, rsp
0x18000cb8f  mov     [rbp+0E0h+var_30], rax
0x18000cb96  mov     rsi, rdx
0x18000cb99  mov     r14d, ecx
0x18000cb9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cba3  lea     r13, WPP_GLOBAL_Control
0x18000cbaa  cmp     rcx, r13
0x18000cbad  jz      short loc_18000CBCA
0x18000cbaf  test    byte ptr [rcx+1Ch], 4
0x18000cbb3  jz      short loc_18000CBCA
0x18000cbb5  mov     rcx, [rcx+10h]
0x18000cbb9  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000cbc0  mov     edx, 18h
0x18000cbc5  call    WPP_SF_
0x18000cbca  xor     edx, edx; Val
0x18000cbcc  mov     [rbp+0E0h+self.ft], 0
0x18000cbd4  mov     r8d, 108h; Size
0x18000cbda  lea     rcx, [rbp+0E0h+self.classDecl]; void *
0x18000cbde  call    memset_0
0x18000cbe3  xor     edx, edx; Val
0x18000cbe5  mov     [rsp+1E0h+instance.ft], 0
0x18000cbee  lea     rcx, [rsp+1E0h+instance.classDecl]; void *
0x18000cbf3  lea     r8d, [rdx+50h]; Size
0x18000cbf7  call    memset_0
0x18000cbfc  mov     rcx, [rsi+38h]; context
0x18000cc00  lea     r8, [rsp+1E0h+instance]; instance
0x18000cc05  lea     rdx, WSP_ReplicationGroup_DeleteObject_rtti; methodDecl
0x18000cc0c  call    MI_Context_ConstructParameters
0x18000cc11  mov     r15d, eax
0x18000cc14  test    eax, eax
0x18000cc16  jnz     short loc_18000CC86
0x18000cc18  mov     rcx, [rsi+38h]; context
0x18000cc1c  lea     r8, [rbp+0E0h+self]; instance
0x18000cc20  lea     rdx, MSFT_StorageExtendedStatus_rtti; classDecl
0x18000cc27  call    MI_Context_ConstructInstance
0x18000cc2c  mov     ebx, eax
0x18000cc2e  test    eax, eax
0x18000cc30  jnz     short loc_18000CC89
0x18000cc32  mov     r8, rsi; struct CWMIContext *
0x18000cc35  lea     rcx, [rbp+0E0h+self]; struct _MSFT_StorageExtendedStatus *
0x18000cc39  mov     edx, r14d; enum _MI_Result
0x18000cc3c  call    ?SrSmapiPopulateStorageExtendedStatus@@YA?AW4_MI_Result@@PEAU_MSFT_StorageExtendedStatus@@W41@AEAVCWMIContext@@@Z; SrSmapiPopulateStorageExtendedStatus(_MSFT_StorageExtendedStatus *,_MI_Result,CWMIContext &)
0x18000cc41  mov     ebx, eax
0x18000cc43  mov     dil, 1
0x18000cc46  test    eax, eax
0x18000cc48  jnz     short loc_18000CC8C
0x18000cc4a  lea     rax, [rbp+0E0h+self]
0x18000cc4e  mov     [rsp+1E0h+var_1C0], ebx
0x18000cc52  mov     [rsp+1E0h+var_1B0], rax
0x18000cc57  lea     r9d, [r15+0Fh]
0x18000cc5b  mov     rax, [rsp+1E0h+instance.ft]
0x18000cc60  lea     r8, [rsp+1E0h+var_1B0]
0x18000cc65  lea     edx, [rbx+1]
0x18000cc68  lea     rcx, [rsp+1E0h+instance]
0x18000cc6d  mov     rax, [rax+50h]
0x18000cc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc76  mov     ebx, eax
0x18000cc78  test    eax, eax
0x18000cc7a  jnz     short loc_18000CC8C
0x18000cc7c  mov     [rbp+0E0h+var_160], r14d
0x18000cc80  mov     [rbp+0E0h+var_15C], dil
0x18000cc84  jmp     short loc_18000CC8C
0x18000cc86  mov     ebx, r15d
0x18000cc89  xor     dil, dil
0x18000cc8c  test    ebx, ebx
0x18000cc8e  jnz     short loc_18000CCA6
0x18000cc90  mov     rcx, [rsi+38h]; self
0x18000cc94  lea     rdx, [rsp+1E0h+instance]
0x18000cc99  call    MI_Instance_Destruct
0x18000cc9e  test    eax, eax
0x18000cca0  mov     ebx, eax
0x18000cca2  cmovz   ebx, r14d
0x18000cca6  test    dil, dil
0x18000cca9  jz      short loc_18000CCB4
0x18000ccab  lea     rcx, [rbp+0E0h+self]; self
0x18000ccaf  call    MI_Instance_Destruct
0x18000ccb4  test    r15d, r15d
0x18000ccb7  jnz     short loc_18000CCC3
0x18000ccb9  lea     rcx, [rsp+1E0h+instance]; self
0x18000ccbe  call    MI_Instance_Destruct
0x18000ccc3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccca  cmp     rcx, r13
0x18000cccd  jz      short loc_18000CCED
0x18000cccf  test    byte ptr [rcx+1Ch], 1
0x18000ccd3  jz      short loc_18000CCED
0x18000ccd5  mov     rcx, [rcx+10h]
0x18000ccd9  lea     r8, WPP_97259de4980931de249eb41af43a46d5_Traceguids
0x18000cce0  mov     edx, 19h
0x18000cce5  mov     r9d, ebx
0x18000cce8  call    WPP_SF_d
0x18000cced  mov     eax, ebx
0x18000ccef  mov     rcx, [rbp+0E0h+var_30]
0x18000ccf6  xor     rcx, rsp; StackCookie
0x18000ccf9  call    __security_check_cookie
0x18000ccfe  lea     r11, [rsp+1E0h+var_20]
0x18000cd06  mov     rbx, [r11+40h]
0x18000cd0a  mov     rsi, [r11+48h]
0x18000cd0e  mov     rsp, r11
0x18000cd11  pop     r15
0x18000cd13  pop     r14
0x18000cd15  pop     r13
0x18000cd17  pop     rdi
0x18000cd18  pop     rbp
0x18000cd19  retn
```
