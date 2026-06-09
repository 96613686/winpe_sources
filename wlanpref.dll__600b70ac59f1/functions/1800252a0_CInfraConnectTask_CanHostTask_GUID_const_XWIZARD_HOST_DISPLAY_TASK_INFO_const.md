# CInfraConnectTask::CanHostTask(_GUID * const,_XWIZARD_HOST_DISPLAY_TASK_INFO * * const)

- ea: `0x1800252a0`
- end: `0x1800253c0`
- name: `?CanHostTask@CInfraConnectTask@@UEAAJQEAU_GUID@@QEAPEAU_XWIZARD_HOST_DISPLAY_TASK_INFO@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(CInfraConnectTask *__hidden this, struct _GUID *const, struct _XWIZARD_HOST_DISPLAY_TASK_INFO **const)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180023054`
- `0x1800252a0`
- `0x18002d80e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800252f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800252f2`

## pseudocode

```c
__int64 __fastcall CInfraConnectTask::CanHostTask(
        CInfraConnectTask *this,
        struct _GUID *const a2,
        struct _XWIZARD_HOST_DISPLAY_TASK_INFO **const a3)
{
  unsigned int v4; // edi
  _DWORD *v5; // rax
  _DWORD *v6; // rbx
  _QWORD *v7; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 10, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids);
  }
  v4 = 0;
  *a3 = 0;
  v5 = CoTaskMemAlloc(0x40u);
  v6 = v5;
  if ( v5 )
  {
    memset_0(v5, 0, 0x40u);
    *v6 = 64;
    v6[1] = 3;
    *((_QWORD *)v6 + 4) = hModule;
    *((_QWORD *)v6 + 5) = 10408;
    *((_QWORD *)v6 + 6) = 10902;
    *((_QWORD *)v6 + 7) = 10903;
    *a3 = (struct _XWIZARD_HOST_DISPLAY_TASK_INFO *)v6;
LABEL_11:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  v4 = -2147024882;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v4;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 145) && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 11, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids);
    goto LABEL_11;
  }
LABEL_12:
  if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 145) >= 4u && (*((_BYTE *)v7 + 148) & 1) != 0 )
    WPP_SF_(v7[17], 12, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids);
  return v4;
}

```

## disassembly

```asm
0x1800252a0  push    rbx
0x1800252a2  push    rsi
0x1800252a3  push    rdi
0x1800252a4  push    r14
0x1800252a6  sub     rsp, 28h
0x1800252aa  mov     rsi, r8
0x1800252ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800252b4  lea     r14, WPP_GLOBAL_Control
0x1800252bb  cmp     rcx, r14
0x1800252be  jz      short loc_1800252EA
0x1800252c0  cmp     byte ptr [rcx+91h], 4
0x1800252c7  jb      short loc_1800252EA
0x1800252c9  test    byte ptr [rcx+94h], 1
0x1800252d0  jz      short loc_1800252EA
0x1800252d2  mov     rcx, [rcx+88h]
0x1800252d9  lea     r8, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids
0x1800252e0  mov     edx, 0Ah
0x1800252e5  call    WPP_SF_
0x1800252ea  xor     edi, edi
0x1800252ec  mov     [rsi], rdi
0x1800252ef  lea     ecx, [rdi+40h]; cb
0x1800252f2  call    cs:__imp_CoTaskMemAlloc
0x1800252f8  mov     rbx, rax
0x1800252fb  test    rax, rax
0x1800252fe  jz      short loc_180025343
0x180025300  xor     edx, edx; Val
0x180025302  lea     r8d, [rdi+40h]; Size
0x180025306  mov     rcx, rax; void *
0x180025309  call    memset_0
0x18002530e  mov     dword ptr [rbx], 40h ; '@'
0x180025314  mov     dword ptr [rbx+4], 3
0x18002531b  mov     rcx, cs:hModule
0x180025322  mov     [rbx+20h], rcx
0x180025326  mov     qword ptr [rbx+28h], 28A8h
0x18002532e  mov     qword ptr [rbx+30h], 2A96h
0x180025336  mov     qword ptr [rbx+38h], 2A97h
0x18002533e  mov     [rsi], rbx
0x180025341  jmp     short loc_18002537E
0x180025343  mov     edi, 8007000Eh
0x180025348  mov     rcx, cs:WPP_GLOBAL_Control
0x18002534f  cmp     rcx, r14
0x180025352  jz      short loc_1800253B4
0x180025354  cmp     byte ptr [rcx+91h], 1
0x18002535b  jb      short loc_180025385
0x18002535d  test    byte ptr [rcx+94h], 1
0x180025364  jz      short loc_180025385
0x180025366  mov     rcx, [rcx+88h]
0x18002536d  lea     r8, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids
0x180025374  mov     edx, 0Bh
0x180025379  call    WPP_SF_
0x18002537e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025385  cmp     rcx, r14
0x180025388  jz      short loc_1800253B4
0x18002538a  cmp     byte ptr [rcx+91h], 4
0x180025391  jb      short loc_1800253B4
0x180025393  test    byte ptr [rcx+94h], 1
0x18002539a  jz      short loc_1800253B4
0x18002539c  mov     rcx, [rcx+88h]
0x1800253a3  lea     r8, WPP_2b4cc797884d339090077a61fdcb28f5_Traceguids
0x1800253aa  mov     edx, 0Ch
0x1800253af  call    WPP_SF_
0x1800253b4  mov     eax, edi
0x1800253b6  add     rsp, 28h
0x1800253ba  pop     r14
0x1800253bc  pop     rdi
0x1800253bd  pop     rsi
0x1800253be  pop     rbx
0x1800253bf  retn
```
