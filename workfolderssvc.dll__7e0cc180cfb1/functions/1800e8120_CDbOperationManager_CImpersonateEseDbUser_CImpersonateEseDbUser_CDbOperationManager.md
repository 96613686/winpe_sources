# CDbOperationManager::CImpersonateEseDbUser::CImpersonateEseDbUser(CDbOperationManager *)

- ea: `0x1800e8120`
- end: `0x1800e82c5`
- name: `??0CImpersonateEseDbUser@CDbOperationManager@@QEAA@PEAV1@@Z`
- size: `421`
- prototype: `__int64 __fastcall(CDbOperationManager::CImpersonateEseDbUser *__hidden this, struct CDbOperationManager *)`
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800e85f4`
- `0x1800e8adc`
- `0x1800e8dc8`
- `0x1800e90e8`
- `0x1800e980c`
- `0x1800ea298`
- `0x1800ea844`
- `0x1800eaad0`
- `0x1800ead0c`

## callees

- `0x18001137c`
- `0x18002dad0`
- `0x1800d7de0`
- `0x1800e8120`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e81a7`
- `KERNEL32!GetLastError` at `0x1800e8241`
- `KERNEL32!GetLastError` at `0x1800e81a7`
- `KERNEL32!GetLastError` at `0x1800e8241`
- `ADVAPI32!SetThreadToken` at `0x1800e8199`
- `ADVAPI32!SetThreadToken` at `0x1800e8237`
- `ADVAPI32!SetThreadToken` at `0x1800e8199`
- `ADVAPI32!SetThreadToken` at `0x1800e8237`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CDbOperationManager::CImpersonateEseDbUser *__fastcall CDbOperationManager::CImpersonateEseDbUser::CImpersonateEseDbUser(
        CDbOperationManager::CImpersonateEseDbUser *this,
        struct CDbOperationManager *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  signed int v5; // eax
  _QWORD *v6; // rcx
  int v7; // edx
  char *v8; // rdx
  signed int LastError; // eax

  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = 0;
  *((_DWORD *)this + 4) = 0;
  v3 = CMetaStoreUtils::OpenThreadTokenForImpersonation((PHANDLE)this + 1);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( v3 == -2147023888 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          91,
          &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
          *(_QWORD *)(*(_QWORD *)this + 72LL));
      v8 = *(char **)(*(_QWORD *)this + 112LL);
      if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL || SetThreadToken(0, v8) )
      {
        v4 = 0;
        goto LABEL_27;
      }
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 92;
        goto LABEL_11;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
        *(_QWORD *)(*(_QWORD *)this + 72LL),
        v3);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
        *(_QWORD *)(*(_QWORD *)this + 72LL));
    if ( !SetThreadToken(0, *(HANDLE *)(*(_QWORD *)this + 112LL)) )
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 90;
LABEL_11:
        WPP_SF_Sd(
          v6[2],
          v7,
          (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
          *(_QWORD *)(*(_QWORD *)this + 72LL),
          v4);
      }
    }
  }
LABEL_27:
  *((_DWORD *)this + 4) = v4;
  return this;
}

```

## disassembly

```asm
0x1800e8120  mov     [rsp+arg_8], rbx
0x1800e8125  mov     [rsp+arg_10], rsi
0x1800e812a  push    rdi
0x1800e812b  sub     rsp, 30h
0x1800e812f  mov     rdi, rcx
0x1800e8132  mov     [rcx], rdx
0x1800e8135  add     rcx, 8; TokenHandle
0x1800e8139  mov     [rsp+38h+arg_0], rcx
0x1800e813e  mov     qword ptr [rcx], 0
0x1800e8145  mov     dword ptr [rdi+10h], 0
0x1800e814c  call    ?OpenThreadTokenForImpersonation@CMetaStoreUtils@@SAJPEAPEAX@Z; CMetaStoreUtils::OpenThreadTokenForImpersonation(void * *)
0x1800e8151  mov     ebx, eax
0x1800e8153  test    eax, eax
0x1800e8155  js      loc_1800E81E4
0x1800e815b  lea     rsi, WPP_GLOBAL_Control
0x1800e8162  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8169  cmp     rcx, rsi
0x1800e816c  jz      short loc_1800E8190
0x1800e816e  test    byte ptr [rcx+1Ch], 4
0x1800e8172  jz      short loc_1800E8190
0x1800e8174  mov     r9, [rdi]
0x1800e8177  mov     edx, 59h ; 'Y'
0x1800e817c  mov     r9, [r9+48h]
0x1800e8180  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e8187  mov     rcx, [rcx+10h]
0x1800e818b  call    WPP_SF_S
0x1800e8190  mov     rdx, [rdi]
0x1800e8193  mov     rdx, [rdx+70h]; Token
0x1800e8197  xor     ecx, ecx; Thread
0x1800e8199  call    cs:__imp_SetThreadToken
0x1800e819f  test    eax, eax
0x1800e81a1  jnz     loc_1800E82AF
0x1800e81a7  call    cs:__imp_GetLastError
0x1800e81ad  mov     ebx, eax
0x1800e81af  test    eax, eax
0x1800e81b1  jle     short loc_1800E81BC
0x1800e81b3  movzx   ebx, ax
0x1800e81b6  or      ebx, 80070000h
0x1800e81bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e81c3  cmp     rcx, rsi
0x1800e81c6  jz      loc_1800E82AF
0x1800e81cc  test    byte ptr [rcx+1Ch], 1
0x1800e81d0  jz      loc_1800E82AF
0x1800e81d6  mov     edx, 5Ah ; 'Z'
0x1800e81db  mov     [rsp+38h+var_18], ebx
0x1800e81df  jmp     loc_1800E8298
0x1800e81e4  cmp     eax, 800703F0h
0x1800e81e9  jnz     loc_1800E8276
0x1800e81ef  lea     rsi, WPP_GLOBAL_Control
0x1800e81f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e81fd  cmp     rcx, rsi
0x1800e8200  jz      short loc_1800E8224
0x1800e8202  test    byte ptr [rcx+1Ch], 4
0x1800e8206  jz      short loc_1800E8224
0x1800e8208  mov     r9, [rdi]
0x1800e820b  mov     edx, 5Bh ; '['
0x1800e8210  mov     r9, [r9+48h]
0x1800e8214  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e821b  mov     rcx, [rcx+10h]
0x1800e821f  call    WPP_SF_S
0x1800e8224  mov     rax, [rdi]
0x1800e8227  mov     rdx, [rax+70h]; Token
0x1800e822b  lea     rax, [rdx-1]
0x1800e822f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e8233  ja      short loc_1800E8272
0x1800e8235  xor     ecx, ecx; Thread
0x1800e8237  call    cs:__imp_SetThreadToken
0x1800e823d  test    eax, eax
0x1800e823f  jnz     short loc_1800E8272
0x1800e8241  call    cs:__imp_GetLastError
0x1800e8247  mov     ebx, eax
0x1800e8249  test    eax, eax
0x1800e824b  jle     short loc_1800E8256
0x1800e824d  movzx   ebx, ax
0x1800e8250  or      ebx, 80070000h
0x1800e8256  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e825d  cmp     rcx, rsi
0x1800e8260  jz      short loc_1800E82AF
0x1800e8262  test    byte ptr [rcx+1Ch], 1
0x1800e8266  jz      short loc_1800E82AF
0x1800e8268  mov     edx, 5Ch ; '\'
0x1800e826d  jmp     loc_1800E81DB
0x1800e8272  xor     ebx, ebx
0x1800e8274  jmp     short loc_1800E82AF
0x1800e8276  lea     rsi, WPP_GLOBAL_Control
0x1800e827d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8284  cmp     rcx, rsi
0x1800e8287  jz      short loc_1800E82AF
0x1800e8289  test    byte ptr [rcx+1Ch], 1
0x1800e828d  jz      short loc_1800E82AF
0x1800e828f  mov     edx, 5Dh ; ']'
0x1800e8294  mov     [rsp+38h+var_18], eax
0x1800e8298  mov     r9, [rdi]
0x1800e829b  mov     r9, [r9+48h]
0x1800e829f  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e82a6  mov     rcx, [rcx+10h]
0x1800e82aa  call    WPP_SF_Sd
0x1800e82af  mov     [rdi+10h], ebx
0x1800e82b2  mov     rax, rdi
0x1800e82b5  mov     rbx, [rsp+38h+arg_8]
0x1800e82ba  mov     rsi, [rsp+38h+arg_10]
0x1800e82bf  add     rsp, 30h
0x1800e82c3  pop     rdi
0x1800e82c4  retn
```
