# NotificationDataPackage::get_Payload(uint *,uchar * *)

- ea: `0x18007f150`
- end: `0x18007f27b`
- name: `?get_Payload@NotificationDataPackage@@UEAAJPEAIPEAPEAE@Z`
- size: `299`
- prototype: `__int64 __fastcall(NotificationDataPackage *__hidden this, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008b67`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18007f150`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f1b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f1b7`

## pseudocode

```c
__int64 __fastcall NotificationDataPackage::get_Payload(
        NotificationDataPackage *this,
        unsigned int *a2,
        unsigned __int8 **a3)
{
  unsigned int v6; // ebx
  SIZE_T v7; // rcx
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rsi
  PVOID *v10; // rcx
  int v12; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_4feb39a99c383ae8f35ff9def979ec7d_Traceguids);
  }
  v6 = 0;
  *a2 = 0;
  *a3 = 0;
  v7 = *((_QWORD *)this + 33) - *((_QWORD *)this + 32);
  if ( !v7 )
    goto LABEL_11;
  v8 = (unsigned __int8 *)CoTaskMemAlloc(v7);
  v9 = v8;
  if ( v8 )
  {
    memcpy_0(v8, *((const void **)this + 32), *((_QWORD *)this + 33) - *((_QWORD *)this + 32));
    *a2 = *((_DWORD *)this + 66) - *((_DWORD *)this + 64);
    *a3 = v9;
    goto LABEL_11;
  }
  v6 = -2147024882;
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x115,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationsdatapackage.cpp",
    (const char *)0x8007000ELL,
    v12);
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_4feb39a99c383ae8f35ff9def979ec7d_Traceguids, 2147942414LL);
LABEL_11:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 49, WPP_4feb39a99c383ae8f35ff9def979ec7d_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18007f150  push    rbx
0x18007f152  push    rsi
0x18007f153  push    rdi
0x18007f154  push    r12
0x18007f156  push    r14
0x18007f158  push    r15
0x18007f15a  sub     rsp, 28h
0x18007f15e  mov     r14, r8
0x18007f161  mov     r15, rdx
0x18007f164  mov     rdi, rcx
0x18007f167  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f16e  lea     r12, WPP_GLOBAL_Control
0x18007f175  cmp     rcx, r12
0x18007f178  jz      short loc_18007F19B
0x18007f17a  test    byte ptr [rcx+1Ch], 2
0x18007f17e  jz      short loc_18007F19B
0x18007f180  cmp     byte ptr [rcx+19h], 6
0x18007f184  jb      short loc_18007F19B
0x18007f186  mov     rcx, [rcx+10h]
0x18007f18a  lea     r8, WPP_4feb39a99c383ae8f35ff9def979ec7d_Traceguids
0x18007f191  mov     edx, 2Fh ; '/'
0x18007f196  call    WPP_SF_
0x18007f19b  xor     ebx, ebx
0x18007f19d  mov     [r15], ebx
0x18007f1a0  mov     [r14], rbx
0x18007f1a3  mov     rcx, [rdi+108h]
0x18007f1aa  sub     rcx, [rdi+100h]; cb
0x18007f1b1  jz      loc_18007F23B
0x18007f1b7  call    cs:__imp_CoTaskMemAlloc
0x18007f1bd  mov     rsi, rax
0x18007f1c0  test    rax, rax
0x18007f1c3  jnz     short loc_18007F210
0x18007f1c5  mov     rcx, [rsp+58h]; this
0x18007f1ca  lea     r8, ?s_HexNumMap@Utils@@0QBDB+10h; unsigned int
0x18007f1d1  mov     ebx, 8007000Eh
0x18007f1d6  mov     edx, 115h; void *
0x18007f1db  mov     r9d, ebx; char *
0x18007f1de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007f1e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f1ea  cmp     rcx, r12
0x18007f1ed  jz      short loc_18007F26B
0x18007f1ef  test    byte ptr [rcx+1Ch], 80h
0x18007f1f3  jz      short loc_18007F242
0x18007f1f5  mov     rcx, [rcx+10h]
0x18007f1f9  lea     edx, [rsi+30h]
0x18007f1fc  mov     r9d, 8007000Eh
0x18007f202  lea     r8, WPP_4feb39a99c383ae8f35ff9def979ec7d_Traceguids
0x18007f209  call    WPP_SF_d
0x18007f20e  jmp     short loc_18007F23B
0x18007f210  mov     rdx, [rdi+100h]; Src
0x18007f217  mov     rcx, rsi; void *
0x18007f21a  mov     r8, [rdi+108h]
0x18007f221  sub     r8, rdx; Size
0x18007f224  call    memcpy_0
0x18007f229  mov     eax, [rdi+108h]
0x18007f22f  sub     eax, [rdi+100h]
0x18007f235  mov     [r15], eax
0x18007f238  mov     [r14], rsi
0x18007f23b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007f242  cmp     rcx, r12
0x18007f245  jz      short loc_18007F26B
0x18007f247  test    byte ptr [rcx+1Ch], 2
0x18007f24b  jz      short loc_18007F26B
0x18007f24d  cmp     byte ptr [rcx+19h], 6
0x18007f251  jb      short loc_18007F26B
0x18007f253  mov     rcx, [rcx+10h]
0x18007f257  lea     r8, WPP_4feb39a99c383ae8f35ff9def979ec7d_Traceguids
0x18007f25e  mov     edx, 31h ; '1'
0x18007f263  mov     r9d, ebx
0x18007f266  call    WPP_SF_d
0x18007f26b  mov     eax, ebx
0x18007f26d  add     rsp, 28h
0x18007f271  pop     r15
0x18007f273  pop     r14
0x18007f275  pop     r12
0x18007f277  pop     rdi
0x18007f278  pop     rsi
0x18007f279  pop     rbx
0x18007f27a  retn
```
