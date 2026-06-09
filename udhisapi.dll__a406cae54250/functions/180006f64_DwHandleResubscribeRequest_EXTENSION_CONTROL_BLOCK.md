# DwHandleResubscribeRequest(_EXTENSION_CONTROL_BLOCK *)

- ea: `0x180006f64`
- end: `0x1800071b6`
- name: `?DwHandleResubscribeRequest@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800071bc`

## callees

- `0x18000249c`
- `0x1800024c4`
- `0x1800025e8`
- `0x1800038ec`
- `0x180006d7c`
- `0x180006f64`
- `0x180007ac8`
- `0x180007d1c`
- `0x1800080bc`
- `0x180009a74`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007183`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000718c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007183`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000718c`

## string_xrefs

- `0x180006f86`: `HTTP_SID`

## pseudocode

```c
__int64 __fastcall DwHandleResubscribeRequest(struct _EXTENSION_CONTROL_BLOCK *a1)
{
  unsigned __int16 *v1; // r14
  unsigned int Header; // ebx
  unsigned int Timeout; // eax
  char *lpszQueryString; // rcx
  int EventingManager; // eax
  int v7; // ebp
  unsigned __int16 *v8; // rax
  int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned int v13; // [rsp+60h] [rbp+8h] BYREF
  void *Block; // [rsp+68h] [rbp+10h] BYREF
  struct IUPnPEventingManager *v15; // [rsp+70h] [rbp+18h] BYREF

  v1 = 0;
  Block = 0;
  v15 = 0;
  a1->dwHttpStatusCode = 200;
  Header = DwQueryHeader(a1, "HTTP_SID", (char **)&Block);
  if ( Header )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_30;
    v11 = 33;
    goto LABEL_29;
  }
  if ( (unsigned int)FIsHeaderPresent(a1, "HTTP_CALLBACK") )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), Header + 30, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids);
    a1->dwHttpStatusCode = 400;
    goto LABEL_31;
  }
  v13 = 0;
  Timeout = DwGetTimeout(a1);
  lpszQueryString = a1->lpszQueryString;
  v13 = Timeout;
  EventingManager = HrGetEventingManager(lpszQueryString, &v15);
  LOBYTE(v7) = EventingManager;
  if ( EventingManager < 0 )
  {
LABEL_22:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)WPP_604df09e42be3037ea2c3a056a88862f_Traceguids,
        (unsigned int)"DwHandleResubscribeRequest",
        v7);
    a1->dwHttpStatusCode = 500;
    goto LABEL_31;
  }
  v8 = WszFromSz((LPCCH)Block);
  v1 = v8;
  if ( !v8 )
  {
    a1->dwHttpStatusCode = 503;
LABEL_31:
    Header = 4;
    goto LABEL_32;
  }
  v9 = (*(__int64 (__fastcall **)(struct IUPnPEventingManager *, unsigned int *, unsigned __int16 *))(*(_QWORD *)v15 + 48LL))(
         v15,
         &v13,
         v8);
  v7 = v9;
  if ( v9 >= 0 )
  {
    Header = DwSendSubscribeResponse(a1, v13, (const char *)Block);
    goto LABEL_21;
  }
  if ( v9 == -2147024895 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_30;
    v11 = 31;
LABEL_29:
    WPP_SF_(v10[2], v11, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids);
LABEL_30:
    a1->dwHttpStatusCode = 412;
    goto LABEL_31;
  }
  if ( v9 == -2147024809 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids);
    a1->dwHttpStatusCode = 412;
    Header = 4;
    v7 = 0;
  }
LABEL_21:
  if ( v7 < 0 )
    goto LABEL_22;
LABEL_32:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, Header);
  free(Block);
  free(v1);
  if ( v15 )
    (*(void (__fastcall **)(struct IUPnPEventingManager *))(*(_QWORD *)v15 + 16LL))(v15);
  return Header;
}

```

## disassembly

```asm
0x180006f64  push    rbx
0x180006f66  push    rbp
0x180006f67  push    rdi
0x180006f68  push    r13
0x180006f6a  push    r14
0x180006f6c  sub     rsp, 30h
0x180006f70  xor     r14d, r14d
0x180006f73  mov     [rsp+58h+Block], 0
0x180006f7c  lea     r8, [rsp+58h+Block]; char **
0x180006f81  mov     [rsp+58h+arg_10], r14
0x180006f86  lea     rdx, aHttpSid; "HTTP_SID"
0x180006f8d  mov     dword ptr [rcx+10h], 0C8h
0x180006f94  mov     rdi, rcx
0x180006f97  call    ?DwQueryHeader@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@PEBDPEAPEAD@Z; DwQueryHeader(_EXTENSION_CONTROL_BLOCK *,char const *,char * *)
0x180006f9c  lea     r13, WPP_GLOBAL_Control
0x180006fa3  mov     ebx, eax
0x180006fa5  test    eax, eax
0x180006fa7  jnz     loc_18000711B
0x180006fad  lea     rdx, aHttpCallback; "HTTP_CALLBACK"
0x180006fb4  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180006fb7  call    ?FIsHeaderPresent@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBD@Z; FIsHeaderPresent(_EXTENSION_CONTROL_BLOCK *,char const *)
0x180006fbc  test    eax, eax
0x180006fbe  jz      short loc_180006FF4
0x180006fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fc7  cmp     rcx, r13
0x180006fca  jz      short loc_180006FE8
0x180006fcc  test    dword ptr [rcx+1Ch], 800h
0x180006fd3  jz      short loc_180006FE8
0x180006fd5  mov     rcx, [rcx+10h]
0x180006fd9  lea     edx, [rbx+1Eh]
0x180006fdc  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x180006fe3  call    WPP_SF_
0x180006fe8  mov     dword ptr [rdi+10h], 190h
0x180006fef  jmp     loc_18000714C
0x180006ff4  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180006ff7  mov     [rsp+58h+arg_0], r14d
0x180006ffc  call    ?DwGetTimeout@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@@Z; DwGetTimeout(_EXTENSION_CONTROL_BLOCK *)
0x180007001  mov     rcx, [rdi+70h]; char *
0x180007005  lea     rdx, [rsp+58h+arg_10]; struct IUPnPEventingManager **
0x18000700a  mov     [rsp+58h+arg_0], eax
0x18000700e  call    ?HrGetEventingManager@@YAJPEADPEAPEAUIUPnPEventingManager@@@Z; HrGetEventingManager(char *,IUPnPEventingManager * *)
0x180007013  mov     ebp, eax
0x180007015  test    eax, eax
0x180007017  js      loc_1800070E0
0x18000701d  mov     rcx, [rsp+58h+Block]; lpMultiByteStr
0x180007022  call    ?WszFromSz@@YAPEAGPEBD@Z; WszFromSz(char const *)
0x180007027  mov     r14, rax
0x18000702a  test    rax, rax
0x18000702d  jnz     short loc_18000703B
0x18000702f  mov     dword ptr [rdi+10h], 1F7h
0x180007036  jmp     loc_18000714C
0x18000703b  mov     rcx, [rsp+58h+arg_10]
0x180007040  lea     rdx, [rsp+58h+arg_0]
0x180007045  mov     r8, r14
0x180007048  mov     rax, [rcx]
0x18000704b  mov     rax, [rax+30h]
0x18000704f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007054  mov     ebp, eax
0x180007056  test    eax, eax
0x180007058  js      short loc_18000706F
0x18000705a  mov     r8, [rsp+58h+Block]; char *
0x18000705f  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180007062  mov     edx, [rsp+58h+arg_0]; unsigned int
0x180007066  call    ?DwSendSubscribeResponse@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@KPEBD@Z; DwSendSubscribeResponse(_EXTENSION_CONTROL_BLOCK *,ulong,char const *)
0x18000706b  mov     ebx, eax
0x18000706d  jmp     short loc_1800070DC
0x18000706f  cmp     eax, 80070001h
0x180007074  jnz     short loc_18000709D
0x180007076  mov     rcx, cs:WPP_GLOBAL_Control
0x18000707d  cmp     rcx, r13
0x180007080  jz      loc_180007145
0x180007086  test    dword ptr [rcx+1Ch], 800h
0x18000708d  jz      loc_180007145
0x180007093  mov     edx, 1Fh
0x180007098  jmp     loc_180007135
0x18000709d  cmp     eax, 80070057h
0x1800070a2  jnz     short loc_1800070DC
0x1800070a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070ab  cmp     rcx, r13
0x1800070ae  jz      short loc_1800070CE
0x1800070b0  test    dword ptr [rcx+1Ch], 800h
0x1800070b7  jz      short loc_1800070CE
0x1800070b9  mov     rcx, [rcx+10h]
0x1800070bd  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x1800070c4  mov     edx, 20h ; ' '
0x1800070c9  call    WPP_SF_
0x1800070ce  mov     dword ptr [rdi+10h], 19Ch
0x1800070d5  mov     ebx, 4
0x1800070da  xor     ebp, ebp
0x1800070dc  test    ebp, ebp
0x1800070de  jns     short loc_180007151
0x1800070e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070e7  cmp     rcx, r13
0x1800070ea  jz      short loc_180007112
0x1800070ec  test    byte ptr [rcx+1Ch], 1
0x1800070f0  jz      short loc_180007112
0x1800070f2  mov     rcx, [rcx+10h]
0x1800070f6  lea     r9, aDwhandleresubs; "DwHandleResubscribeRequest"
0x1800070fd  mov     edx, 22h ; '"'
0x180007102  mov     [rsp+58h+var_38], ebp
0x180007106  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x18000710d  call    WPP_SF_sd
0x180007112  mov     dword ptr [rdi+10h], 1F4h
0x180007119  jmp     short loc_18000714C
0x18000711b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007122  cmp     rcx, r13
0x180007125  jz      short loc_180007145
0x180007127  test    dword ptr [rcx+1Ch], 800h
0x18000712e  jz      short loc_180007145
0x180007130  mov     edx, 21h ; '!'
0x180007135  mov     rcx, [rcx+10h]
0x180007139  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x180007140  call    WPP_SF_
0x180007145  mov     dword ptr [rdi+10h], 19Ch
0x18000714c  mov     ebx, 4
0x180007151  mov     rcx, cs:WPP_GLOBAL_Control
0x180007158  cmp     rcx, r13
0x18000715b  jz      short loc_18000717E
0x18000715d  test    dword ptr [rcx+1Ch], 800h
0x180007164  jz      short loc_18000717E
0x180007166  mov     rcx, [rcx+10h]
0x18000716a  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x180007171  mov     edx, 23h ; '#'
0x180007176  mov     r9d, ebx
0x180007179  call    WPP_SF_d
0x18000717e  mov     rcx, [rsp+58h+Block]; Block
0x180007183  call    cs:__imp_free
0x180007189  mov     rcx, r14; Block
0x18000718c  call    cs:__imp_free
0x180007192  mov     rcx, [rsp+58h+arg_10]
0x180007197  test    rcx, rcx
0x18000719a  jz      short loc_1800071A8
0x18000719c  mov     rax, [rcx]
0x18000719f  mov     rax, [rax+10h]
0x1800071a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071a8  mov     eax, ebx
0x1800071aa  add     rsp, 30h
0x1800071ae  pop     r14
0x1800071b0  pop     r13
0x1800071b2  pop     rdi
0x1800071b3  pop     rbp
0x1800071b4  pop     rbx
0x1800071b5  retn
```
