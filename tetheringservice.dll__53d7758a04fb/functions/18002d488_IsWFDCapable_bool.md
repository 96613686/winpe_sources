# IsWFDCapable(bool *)

- ea: `0x18002d488`
- end: `0x18002d666`
- name: `?IsWFDCapable@@YAJPEA_N@Z`
- size: `478`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002d868`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x18000bfb4`
- `0x18002d488`

## import_xrefs

- `wlanapi!WFDQueryPropertyInt` at `0x18002d567`
- `wlanapi!WFDQueryPropertyInt` at `0x18002d567`
- `wlanapi!WFDOpenHandleInt` at `0x18002d50f`
- `wlanapi!WFDOpenHandleInt` at `0x18002d50f`
- `wlanapi!WlanFreeMemory` at `0x18002d603`
- `wlanapi!WlanFreeMemory` at `0x18002d603`
- `wlanapi!WFDCloseHandleInt` at `0x18002d624`
- `wlanapi!WFDCloseHandleInt` at `0x18002d624`

## pseudocode

```c
__int64 __fastcall IsWFDCapable(bool *a1)
{
  TetheringServiceTelemetry *v2; // rcx
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // r9
  __int64 v6; // rdx
  int v7; // eax
  int v9; // [rsp+50h] [rbp+30h] BYREF
  int v10; // [rsp+58h] [rbp+38h] BYREF
  __int64 v11; // [rsp+60h] [rbp+40h] BYREF
  PVOID pMemory; // [rsp+68h] [rbp+48h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v9 = 0;
  v11 = 0;
  v10 = 0;
  pMemory = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    goto LABEL_32;
  }
  *a1 = 0;
  v4 = WFDOpenHandleInt(1, &v9, &v11);
  v3 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_28;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_25;
    v6 = 31;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v2 + 2), v6, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids, v3);
    goto LABEL_24;
  }
  v7 = WFDQueryPropertyInt(v11, 3, &v10, &pMemory);
  v3 = v7;
  if ( !v7 )
  {
    v3 = 0;
    *a1 = 1;
    goto LABEL_24;
  }
  if ( v7 != 5023 )
  {
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      goto LABEL_28;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_25;
    v6 = 33;
    goto LABEL_12;
  }
  v3 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_25:
      if ( v2 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      {
        LOBYTE(v5) = *a1;
        WPP_SF_c(*((_QWORD *)v2 + 2), 34, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids, v5);
        v2 = WPP_GLOBAL_Control;
      }
      goto LABEL_28;
    }
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids);
LABEL_24:
    v2 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
LABEL_28:
  if ( pMemory )
  {
    WlanFreeMemory(pMemory);
    v2 = WPP_GLOBAL_Control;
    pMemory = 0;
  }
  if ( v11 )
  {
    WFDCloseHandleInt(v11);
    v2 = WPP_GLOBAL_Control;
    v11 = 0;
  }
LABEL_32:
  if ( v2 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v2 + 2), 35, &WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18002d488  push    rbp
0x18002d48a  push    rbx
0x18002d48b  push    rdi
0x18002d48c  push    r14
0x18002d48e  push    r15
0x18002d490  mov     rbp, rsp
0x18002d493  sub     rsp, 20h
0x18002d497  mov     rdi, rcx
0x18002d49a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4a1  lea     r14, WPP_GLOBAL_Control
0x18002d4a8  lea     r15, WPP_2689d87eb4dd3de7cf6975b0eac370f5_Traceguids
0x18002d4af  cmp     rcx, r14
0x18002d4b2  jz      short loc_18002D4D2
0x18002d4b4  test    byte ptr [rcx+1Ch], 8
0x18002d4b8  jz      short loc_18002D4D2
0x18002d4ba  mov     rcx, [rcx+10h]
0x18002d4be  mov     edx, 1Eh
0x18002d4c3  mov     r8, r15
0x18002d4c6  call    WPP_SF_
0x18002d4cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4d2  mov     [rbp+arg_0], 0
0x18002d4d9  mov     [rbp+arg_10], 0
0x18002d4e1  mov     [rbp+arg_8], 0
0x18002d4e8  mov     [rbp+pMemory], 0
0x18002d4f0  test    rdi, rdi
0x18002d4f3  jnz     short loc_18002D4FF
0x18002d4f5  mov     ebx, 80070057h
0x18002d4fa  jmp     loc_18002D639
0x18002d4ff  lea     r8, [rbp+arg_10]
0x18002d503  mov     byte ptr [rdi], 0
0x18002d506  lea     rdx, [rbp+arg_0]
0x18002d50a  mov     ecx, 1
0x18002d50f  call    cs:__imp_WFDOpenHandleInt
0x18002d515  mov     ebx, eax
0x18002d517  test    eax, eax
0x18002d519  jz      short loc_18002D556
0x18002d51b  jle     short loc_18002D526
0x18002d51d  movzx   ebx, ax
0x18002d520  or      ebx, 80070000h
0x18002d526  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d52d  cmp     rcx, r14
0x18002d530  jz      loc_18002D5F7
0x18002d536  test    byte ptr [rcx+1Ch], 1
0x18002d53a  jz      loc_18002D5D1
0x18002d540  mov     edx, 1Fh
0x18002d545  mov     rcx, [rcx+10h]
0x18002d549  mov     r9d, ebx
0x18002d54c  mov     r8, r15
0x18002d54f  call    WPP_SF_d
0x18002d554  jmp     short loc_18002D5CA
0x18002d556  mov     rcx, [rbp+arg_10]
0x18002d55a  lea     r9, [rbp+pMemory]
0x18002d55e  lea     r8, [rbp+arg_8]
0x18002d562  mov     edx, 3
0x18002d567  call    cs:__imp_WFDQueryPropertyInt
0x18002d56d  mov     ebx, eax
0x18002d56f  test    eax, eax
0x18002d571  jz      short loc_18002D5C5
0x18002d573  cmp     eax, 139Fh
0x18002d578  jnz     short loc_18002D59F
0x18002d57a  xor     ebx, ebx
0x18002d57c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d583  cmp     rcx, r14
0x18002d586  jz      short loc_18002D5F7
0x18002d588  test    byte ptr [rcx+1Ch], 2
0x18002d58c  jz      short loc_18002D5D1
0x18002d58e  mov     rcx, [rcx+10h]
0x18002d592  lea     edx, [rbx+20h]
0x18002d595  mov     r8, r15
0x18002d598  call    WPP_SF_
0x18002d59d  jmp     short loc_18002D5CA
0x18002d59f  test    eax, eax
0x18002d5a1  jle     short loc_18002D5AC
0x18002d5a3  movzx   ebx, ax
0x18002d5a6  or      ebx, 80070000h
0x18002d5ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5b3  cmp     rcx, r14
0x18002d5b6  jz      short loc_18002D5F7
0x18002d5b8  test    byte ptr [rcx+1Ch], 1
0x18002d5bc  jz      short loc_18002D5D1
0x18002d5be  mov     edx, 21h ; '!'
0x18002d5c3  jmp     short loc_18002D545
0x18002d5c5  xor     ebx, ebx
0x18002d5c7  mov     byte ptr [rdi], 1
0x18002d5ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5d1  cmp     rcx, r14
0x18002d5d4  jz      short loc_18002D5F7
0x18002d5d6  test    byte ptr [rcx+1Ch], 8
0x18002d5da  jz      short loc_18002D5F7
0x18002d5dc  mov     r9b, [rdi]
0x18002d5df  mov     edx, 22h ; '"'
0x18002d5e4  mov     rcx, [rcx+10h]
0x18002d5e8  mov     r8, r15
0x18002d5eb  call    WPP_SF_c
0x18002d5f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5f7  mov     rax, [rbp+pMemory]
0x18002d5fb  test    rax, rax
0x18002d5fe  jz      short loc_18002D618
0x18002d600  mov     rcx, rax; pMemory
0x18002d603  call    cs:__imp_WlanFreeMemory
0x18002d609  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d610  mov     [rbp+pMemory], 0
0x18002d618  mov     rax, [rbp+arg_10]
0x18002d61c  test    rax, rax
0x18002d61f  jz      short loc_18002D639
0x18002d621  mov     rcx, rax
0x18002d624  call    cs:__imp_WFDCloseHandleInt
0x18002d62a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d631  mov     [rbp+arg_10], 0
0x18002d639  cmp     rcx, r14
0x18002d63c  jz      short loc_18002D658
0x18002d63e  test    byte ptr [rcx+1Ch], 8
0x18002d642  jz      short loc_18002D658
0x18002d644  mov     rcx, [rcx+10h]
0x18002d648  mov     edx, 23h ; '#'
0x18002d64d  mov     r9d, ebx
0x18002d650  mov     r8, r15
0x18002d653  call    WPP_SF_d
0x18002d658  mov     eax, ebx
0x18002d65a  add     rsp, 20h
0x18002d65e  pop     r15
0x18002d660  pop     r14
0x18002d662  pop     rdi
0x18002d663  pop     rbx
0x18002d664  pop     rbp
0x18002d665  retn
```
