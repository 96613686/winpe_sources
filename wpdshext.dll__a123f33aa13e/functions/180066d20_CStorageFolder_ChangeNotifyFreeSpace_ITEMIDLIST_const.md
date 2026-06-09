# CStorageFolder::_ChangeNotifyFreeSpace(_ITEMIDLIST const *)

- ea: `0x180066d20`
- end: `0x180066ed1`
- name: `?_ChangeNotifyFreeSpace@CStorageFolder@@EEAAJPEFBU_ITEMIDLIST@@@Z`
- size: `433`
- prototype: `__int64 __fastcall(CStorageFolder *__hidden this, const struct _ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800287d0`
- `0x18002ff5c`
- `0x180035590`
- `0x180066d20`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180066e97`
- `ole32!CoTaskMemFree` at `0x180066ea3`
- `ole32!CoTaskMemFree` at `0x180066e97`
- `ole32!CoTaskMemFree` at `0x180066ea3`
- `SHELL32!SHChangeNotify` at `0x180066e8b`
- `SHELL32!SHChangeNotify` at `0x180066e8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CStorageFolder::_ChangeNotifyFreeSpace(CStorageFolder *this, const struct _ITEMIDLIST *a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  PVOID *v5; // rcx
  __int64 v6; // rdx
  LPCVOID dwItem1; // [rsp+40h] [rbp-238h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-230h] BYREF
  _BYTE v10[528]; // [rsp+50h] [rbp-228h] BYREF

  pv = 0;
  dwItem1 = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
LABEL_16:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  v4 = (*(__int64 (__fastcall **)(CStorageFolder *, const struct _ITEMIDLIST *, _BYTE *, __int64))(*(_QWORD *)this
                                                                                                 + 184LL))(
         this,
         a2,
         v10,
         260);
  v3 = v4;
  if ( v4 < 0 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_21;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_17;
    v6 = 163;
LABEL_15:
    WPP_SF_d(v5[2], v6, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, (unsigned int)v4);
    goto LABEL_16;
  }
  v4 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, _BYTE *, _QWORD, LPVOID *, _QWORD))(*((_QWORD *)this + 2)
                                                                                            + 24LL))(
         (char *)this + 16,
         0,
         0,
         v10,
         0,
         &pv,
         0);
  v3 = v4;
  if ( v4 < 0 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_21;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_17;
    v6 = 164;
    goto LABEL_15;
  }
  v4 = SHILCombine(*((_QWORD *)this + 8), pv, &dwItem1);
  v3 = v4;
  if ( v4 >= 0 )
  {
    SHChangeNotify(0x2000, 0, dwItem1, 0);
    goto LABEL_21;
  }
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_17:
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
        WPP_SF_d(v5[2], 166, WPP_9caa288f52d13f713777aed0becde05d_Traceguids, v3);
      goto LABEL_21;
    }
    v6 = 165;
    goto LABEL_15;
  }
LABEL_21:
  CoTaskMemFree((LPVOID)dwItem1);
  CoTaskMemFree(pv);
  return v3;
}

```

## disassembly

```asm
0x180066d20  mov     [rsp+arg_10], rbx
0x180066d25  mov     [rsp+arg_18], rdi
0x180066d2a  push    r14
0x180066d2c  sub     rsp, 270h
0x180066d33  mov     rax, cs:__security_cookie
0x180066d3a  xor     rax, rsp
0x180066d3d  mov     [rsp+278h+var_18], rax
0x180066d45  mov     rdi, rcx
0x180066d48  mov     [rsp+278h+pv], 0
0x180066d51  mov     [rsp+278h+dwItem1], 0
0x180066d5a  lea     r14, WPP_GLOBAL_Control
0x180066d61  test    rdx, rdx
0x180066d64  jnz     short loc_180066D70
0x180066d66  mov     ebx, 80070057h
0x180066d6b  jmp     loc_180066E50
0x180066d70  mov     rax, [rcx]
0x180066d73  mov     r9d, 104h
0x180066d79  lea     r8, [rsp+278h+var_228]
0x180066d7e  mov     rax, [rax+0B8h]
0x180066d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066d8a  mov     ebx, eax
0x180066d8c  test    eax, eax
0x180066d8e  jns     short loc_180066DB4
0x180066d90  mov     rcx, cs:WPP_GLOBAL_Control
0x180066d97  cmp     rcx, r14
0x180066d9a  jz      loc_180066E92
0x180066da0  test    byte ptr [rcx+1Ch], 2
0x180066da4  jz      loc_180066E57
0x180066daa  mov     edx, 0A3h
0x180066daf  jmp     loc_180066E3D
0x180066db4  lea     rcx, [rdi+10h]
0x180066db8  mov     rax, [rcx]
0x180066dbb  mov     [rsp+278h+var_248], 0
0x180066dc4  lea     rdx, [rsp+278h+pv]
0x180066dc9  mov     [rsp+278h+var_250], rdx
0x180066dce  mov     [rsp+278h+var_258], 0
0x180066dd7  lea     r9, [rsp+278h+var_228]
0x180066ddc  xor     r8d, r8d
0x180066ddf  xor     edx, edx
0x180066de1  mov     rax, [rax+18h]
0x180066de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066dea  mov     ebx, eax
0x180066dec  test    eax, eax
0x180066dee  jns     short loc_180066E0D
0x180066df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180066df7  cmp     rcx, r14
0x180066dfa  jz      loc_180066E92
0x180066e00  test    byte ptr [rcx+1Ch], 2
0x180066e04  jz      short loc_180066E57
0x180066e06  mov     edx, 0A4h
0x180066e0b  jmp     short loc_180066E3D
0x180066e0d  lea     r8, [rsp+278h+dwItem1]
0x180066e12  mov     rdx, [rsp+278h+pv]
0x180066e17  mov     rcx, [rdi+40h]
0x180066e1b  call    SHILCombine
0x180066e20  mov     ebx, eax
0x180066e22  test    eax, eax
0x180066e24  jns     short loc_180066E7C
0x180066e26  mov     rcx, cs:WPP_GLOBAL_Control
0x180066e2d  cmp     rcx, r14
0x180066e30  jz      short loc_180066E92
0x180066e32  test    byte ptr [rcx+1Ch], 2
0x180066e36  jz      short loc_180066E57
0x180066e38  mov     edx, 0A5h
0x180066e3d  mov     r9d, eax
0x180066e40  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180066e47  mov     rcx, [rcx+10h]
0x180066e4b  call    WPP_SF_d
0x180066e50  mov     rcx, cs:WPP_GLOBAL_Control
0x180066e57  cmp     rcx, r14
0x180066e5a  jz      short loc_180066E92
0x180066e5c  test    byte ptr [rcx+1Ch], 2
0x180066e60  jz      short loc_180066E92
0x180066e62  mov     edx, 0A6h
0x180066e67  mov     r9d, ebx
0x180066e6a  lea     r8, WPP_9caa288f52d13f713777aed0becde05d_Traceguids
0x180066e71  mov     rcx, [rcx+10h]
0x180066e75  call    WPP_SF_d
0x180066e7a  jmp     short loc_180066E92
0x180066e7c  xor     r9d, r9d; dwItem2
0x180066e7f  mov     r8, [rsp+278h+dwItem1]; dwItem1
0x180066e84  xor     edx, edx; uFlags
0x180066e86  mov     ecx, 2000h; wEventId
0x180066e8b  call    cs:__imp_SHChangeNotify
0x180066e91  nop
0x180066e92  mov     rcx, [rsp+278h+dwItem1]; pv
0x180066e97  call    cs:__imp_CoTaskMemFree
0x180066e9d  nop
0x180066e9e  mov     rcx, [rsp+278h+pv]; pv
0x180066ea3  call    cs:__imp_CoTaskMemFree
0x180066ea9  mov     eax, ebx
0x180066eab  mov     rcx, [rsp+278h+var_18]
0x180066eb3  xor     rcx, rsp; StackCookie
0x180066eb6  call    __security_check_cookie
0x180066ebb  lea     r11, [rsp+278h+var_8]
0x180066ec3  mov     rbx, [r11+20h]
0x180066ec7  mov     rdi, [r11+28h]
0x180066ecb  mov     rsp, r11
0x180066ece  pop     r14
0x180066ed0  retn
```
