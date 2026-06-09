# CWNPNet::GetUserById(unsigned __int64,_NotificationUser * *)

- ea: `0x180038e74`
- end: `0x180038fa1`
- name: `?GetUserById@CWNPNet@@QEAAJ_KPEAPEAU_NotificationUser@@@Z`
- size: `301`
- prototype: `__int64 __fastcall(CWNPNet *this, __int64, struct _NotificationUser **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024fe0`

## callees

- `0x18000fe2c`
- `0x18000fe54`
- `0x180038e74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038f55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038f55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038ec8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038ec8`

## pseudocode

```c
__int64 __fastcall CWNPNet::GetUserById(CWNPNet *this, __int64 a2, struct _NotificationUser **a3)
{
  struct _NotificationUser *v6; // rax
  struct _NotificationUser *v7; // rbx
  __int64 *i; // rcx
  __int64 v9; // rax
  struct _NotificationUser *v10; // rax
  unsigned int v11; // edi

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids);
  }
  *a3 = 0;
  v6 = (struct _NotificationUser *)CoTaskMemAlloc(0x10u);
  v7 = v6;
  if ( v6 )
  {
    *(_OWORD *)v6 = 0;
    for ( i = (__int64 *)*((_QWORD *)this + 200); i != (__int64 *)((char *)this + 1600); i = (__int64 *)*i )
    {
      v9 = i[2];
      if ( v9 == a2 )
      {
        *(_QWORD *)v7 = v9;
        *((_DWORD *)v7 + 2) = *((_DWORD *)i + 6);
        *((_DWORD *)v7 + 3) = *((_DWORD *)i + 7);
        v10 = v7;
        v7 = 0;
        *a3 = v10;
        v11 = 0;
        goto LABEL_12;
      }
    }
    v11 = -2013002772;
LABEL_12:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, v11);
    }
    if ( v7 )
      CoTaskMemFree(v7);
    return v11;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids, 2147942414LL);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180038e74  push    rbx
0x180038e76  push    rbp
0x180038e77  push    rsi
0x180038e78  push    rdi
0x180038e79  push    r15
0x180038e7b  sub     rsp, 20h
0x180038e7f  mov     rdi, r8
0x180038e82  mov     rbp, rdx
0x180038e85  mov     rsi, rcx
0x180038e88  mov     rcx, cs:WPP_GLOBAL_Control
0x180038e8f  lea     r15, WPP_GLOBAL_Control
0x180038e96  cmp     rcx, r15
0x180038e99  jz      short loc_180038EBC
0x180038e9b  test    byte ptr [rcx+1Ch], 4
0x180038e9f  jz      short loc_180038EBC
0x180038ea1  cmp     byte ptr [rcx+19h], 6
0x180038ea5  jb      short loc_180038EBC
0x180038ea7  mov     rcx, [rcx+10h]
0x180038eab  lea     r8, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x180038eb2  mov     edx, 93h
0x180038eb7  call    WPP_SF_
0x180038ebc  mov     ecx, 10h; cb
0x180038ec1  mov     qword ptr [rdi], 0
0x180038ec8  call    cs:__imp_CoTaskMemAlloc
0x180038ece  mov     rbx, rax
0x180038ed1  test    rax, rax
0x180038ed4  jz      loc_180038F5F
0x180038eda  xorps   xmm0, xmm0
0x180038edd  lea     rdx, [rsi+640h]
0x180038ee4  movups  xmmword ptr [rax], xmm0
0x180038ee7  mov     rcx, [rdx]
0x180038eea  cmp     rcx, rdx
0x180038eed  jz      short loc_180038F18
0x180038eef  mov     rax, [rcx+10h]
0x180038ef3  cmp     rax, rbp
0x180038ef6  jz      short loc_180038EFD
0x180038ef8  mov     rcx, [rcx]
0x180038efb  jmp     short loc_180038EEA
0x180038efd  mov     [rbx], rax
0x180038f00  mov     eax, [rcx+18h]
0x180038f03  mov     [rbx+8], eax
0x180038f06  mov     eax, [rcx+1Ch]
0x180038f09  mov     [rbx+0Ch], eax
0x180038f0c  mov     rax, rbx
0x180038f0f  xor     ebx, ebx
0x180038f11  mov     [rdi], rax
0x180038f14  xor     edi, edi
0x180038f16  jmp     short loc_180038F1D
0x180038f18  mov     edi, 880403ECh
0x180038f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f24  cmp     rcx, r15
0x180038f27  jz      short loc_180038F4D
0x180038f29  test    byte ptr [rcx+1Ch], 4
0x180038f2d  jz      short loc_180038F4D
0x180038f2f  cmp     byte ptr [rcx+19h], 6
0x180038f33  jb      short loc_180038F4D
0x180038f35  mov     rcx, [rcx+10h]
0x180038f39  lea     r8, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x180038f40  mov     edx, 95h
0x180038f45  mov     r9d, edi
0x180038f48  call    WPP_SF_d
0x180038f4d  test    rbx, rbx
0x180038f50  jz      short loc_180038F5B
0x180038f52  mov     rcx, rbx; pv
0x180038f55  call    cs:__imp_CoTaskMemFree
0x180038f5b  mov     eax, edi
0x180038f5d  jmp     short loc_180038F96
0x180038f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180038f66  mov     ebx, 8007000Eh
0x180038f6b  cmp     rcx, r15
0x180038f6e  jz      short loc_180038F94
0x180038f70  test    byte ptr [rcx+1Ch], 4
0x180038f74  jz      short loc_180038F94
0x180038f76  cmp     byte ptr [rcx+19h], 2
0x180038f7a  jb      short loc_180038F94
0x180038f7c  mov     rcx, [rcx+10h]
0x180038f80  lea     r8, WPP_4e47059d20e03c0ffeb37878b8bdc70f_Traceguids
0x180038f87  mov     edx, 94h
0x180038f8c  mov     r9d, ebx
0x180038f8f  call    WPP_SF_d
0x180038f94  mov     eax, ebx
0x180038f96  add     rsp, 20h
0x180038f9a  pop     r15
0x180038f9c  pop     rdi
0x180038f9d  pop     rsi
0x180038f9e  pop     rbp
0x180038f9f  pop     rbx
0x180038fa0  retn
```
