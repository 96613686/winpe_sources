# CInfraCreateTask::CanHostTask(_GUID * const,_XWIZARD_HOST_DISPLAY_TASK_INFO * * const)

- ea: `0x180024d80`
- end: `0x180024f41`
- name: `?CanHostTask@CInfraCreateTask@@UEAAJQEAU_GUID@@QEAPEAU_XWIZARD_HOST_DISPLAY_TASK_INFO@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(CInfraCreateTask *__hidden this, struct _GUID *const, struct _XWIZARD_HOST_DISPLAY_TASK_INFO **const)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180020800`
- `0x180023054`
- `0x180023eec`
- `0x180024d80`
- `0x180025d10`
- `0x18002d80e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024e9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024e9d`

## pseudocode

```c
__int64 __fastcall CInfraCreateTask::CanHostTask(
        CInfraCreateTask *this,
        struct _GUID *const a2,
        struct _XWIZARD_HOST_DISPLAY_TASK_INFO **const a3)
{
  int WlanInterfaces; // eax
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  __int128 v10; // [rsp+20h] [rbp-58h] BYREF
  __int64 v11; // [rsp+30h] [rbp-48h]
  __int128 v12; // [rsp+38h] [rbp-40h]
  int v13; // [rsp+48h] [rbp-30h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 10, WPP_6be65949477a331d287e6272b304cda0_Traceguids);
  }
  *a3 = 0;
  v11 = 0;
  v13 = 10;
  v10 = 0;
  v12 = 0;
  WlanInterfaces = GetWlanInterfaces((struct CInterfaces *)&v10);
  v5 = WlanInterfaces;
  if ( WlanInterfaces < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 145)
      || (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) == 0 )
    {
      goto LABEL_11;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      11,
      WPP_6be65949477a331d287e6272b304cda0_Traceguids,
      (unsigned int)WlanInterfaces);
LABEL_10:
    v6 = WPP_GLOBAL_Control;
LABEL_11:
    v5 = 1;
    goto LABEL_12;
  }
  if ( !v11 )
    goto LABEL_10;
  v8 = CoTaskMemAlloc(0x40u);
  v9 = v8;
  if ( v8 )
  {
    memset_0(v8, 0, 0x40u);
    *v9 = 64;
    v9[1] = 3;
    *((_QWORD *)v9 + 4) = hModule;
    *((_QWORD *)v9 + 5) = 102;
    *((_QWORD *)v9 + 6) = 10902;
    *((_QWORD *)v9 + 7) = 10903;
    *a3 = (struct _XWIZARD_HOST_DISPLAY_TASK_INFO *)v9;
LABEL_24:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  v5 = -2147024882;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_16;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 145) && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 12, WPP_6be65949477a331d287e6272b304cda0_Traceguids);
    goto LABEL_24;
  }
LABEL_12:
  if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 145) >= 4u && (*((_BYTE *)v6 + 148) & 1) != 0 )
    WPP_SF_(v6[17], 13, WPP_6be65949477a331d287e6272b304cda0_Traceguids);
LABEL_16:
  CInterfaces::~CInterfaces((CInterfaces *)&v10);
  return v5;
}

```

## disassembly

```asm
0x180024d80  push    rbx
0x180024d82  push    rsi
0x180024d83  push    rdi
0x180024d84  push    r15
0x180024d86  sub     rsp, 58h
0x180024d8a  mov     rsi, r8
0x180024d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d94  lea     r15, WPP_GLOBAL_Control
0x180024d9b  mov     ebx, 0Ah
0x180024da0  cmp     rcx, r15
0x180024da3  jz      short loc_180024DCC
0x180024da5  cmp     byte ptr [rcx+91h], 4
0x180024dac  jb      short loc_180024DCC
0x180024dae  test    byte ptr [rcx+94h], 1
0x180024db5  jz      short loc_180024DCC
0x180024db7  mov     rcx, [rcx+88h]
0x180024dbe  lea     r8, WPP_6be65949477a331d287e6272b304cda0_Traceguids
0x180024dc5  mov     edx, ebx
0x180024dc7  call    WPP_SF_
0x180024dcc  xorps   xmm0, xmm0
0x180024dcf  mov     qword ptr [rsi], 0
0x180024dd6  xorps   xmm1, xmm1
0x180024dd9  mov     [rsp+78h+var_48], 0
0x180024de2  lea     rcx, [rsp+78h+var_58]; this
0x180024de7  mov     [rsp+78h+var_30], ebx
0x180024deb  movdqu  [rsp+78h+var_58], xmm0
0x180024df1  movdqu  [rsp+78h+var_40], xmm1
0x180024df7  call    ?GetWlanInterfaces@@YAJAEAVCInterfaces@@@Z; GetWlanInterfaces(CInterfaces &)
0x180024dfc  mov     edi, eax
0x180024dfe  test    eax, eax
0x180024e00  jns     loc_180024E90
0x180024e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e0d  cmp     rcx, r15
0x180024e10  jz      short loc_180024E46
0x180024e12  cmp     byte ptr [rcx+91h], 1
0x180024e19  jb      short loc_180024E46
0x180024e1b  test    byte ptr [rcx+94h], 1
0x180024e22  jz      short loc_180024E46
0x180024e24  mov     rcx, [rcx+88h]
0x180024e2b  lea     r8, WPP_6be65949477a331d287e6272b304cda0_Traceguids
0x180024e32  mov     edx, 0Bh
0x180024e37  mov     r9d, eax
0x180024e3a  call    WPP_SF_d
0x180024e3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e46  mov     edi, 1
0x180024e4b  cmp     rcx, r15
0x180024e4e  jz      short loc_180024E7A
0x180024e50  cmp     byte ptr [rcx+91h], 4
0x180024e57  jb      short loc_180024E7A
0x180024e59  test    byte ptr [rcx+94h], 1
0x180024e60  jz      short loc_180024E7A
0x180024e62  mov     rcx, [rcx+88h]
0x180024e69  lea     r8, WPP_6be65949477a331d287e6272b304cda0_Traceguids
0x180024e70  mov     edx, 0Dh
0x180024e75  call    WPP_SF_
0x180024e7a  lea     rcx, [rsp+78h+var_58]; this
0x180024e7f  call    ??1CInterfaces@@QEAA@XZ; CInterfaces::~CInterfaces(void)
0x180024e84  mov     eax, edi
0x180024e86  add     rsp, 58h
0x180024e8a  pop     r15
0x180024e8c  pop     rdi
0x180024e8d  pop     rsi
0x180024e8e  pop     rbx
0x180024e8f  retn
0x180024e90  cmp     [rsp+78h+var_48], 0
0x180024e96  jz      short loc_180024E3F
0x180024e98  mov     ecx, 40h ; '@'; cb
0x180024e9d  call    cs:__imp_CoTaskMemAlloc
0x180024ea3  mov     rbx, rax
0x180024ea6  test    rax, rax
0x180024ea9  jz      short loc_180024EEE
0x180024eab  xor     edx, edx; Val
0x180024ead  mov     rcx, rax; void *
0x180024eb0  lea     r8d, [rdx+40h]; Size
0x180024eb4  call    memset_0
0x180024eb9  mov     dword ptr [rbx], 40h ; '@'
0x180024ebf  mov     dword ptr [rbx+4], 3
0x180024ec6  mov     rcx, cs:hModule
0x180024ecd  mov     [rbx+20h], rcx
0x180024ed1  mov     qword ptr [rbx+28h], 66h ; 'f'
0x180024ed9  mov     qword ptr [rbx+30h], 2A96h
0x180024ee1  mov     qword ptr [rbx+38h], 2A97h
0x180024ee9  mov     [rsi], rbx
0x180024eec  jmp     short loc_180024F35
0x180024eee  mov     edi, 8007000Eh
0x180024ef3  mov     rcx, cs:WPP_GLOBAL_Control
0x180024efa  cmp     rcx, r15
0x180024efd  jz      loc_180024E7A
0x180024f03  cmp     byte ptr [rcx+91h], 1
0x180024f0a  jb      loc_180024E4B
0x180024f10  test    byte ptr [rcx+94h], 1
0x180024f17  jz      loc_180024E4B
0x180024f1d  mov     rcx, [rcx+88h]
0x180024f24  lea     r8, WPP_6be65949477a331d287e6272b304cda0_Traceguids
0x180024f2b  mov     edx, 0Ch
0x180024f30  call    WPP_SF_
0x180024f35  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f3c  jmp     loc_180024E4B
```
