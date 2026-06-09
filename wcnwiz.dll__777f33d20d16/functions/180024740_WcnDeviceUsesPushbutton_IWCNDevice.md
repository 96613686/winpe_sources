# WcnDeviceUsesPushbutton(IWCNDevice *)

- ea: `0x180024740`
- end: `0x18002494c`
- name: `?WcnDeviceUsesPushbutton@@YA_NPEAUIWCNDevice@@@Z`
- size: `524`
- prototype: `bool __fastcall(struct IWCNDevice *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023198`

## callees

- `0x18000e1dc`
- `0x180024740`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `KERNEL32!RegGetValueW` at `0x180024896`
- `KERNEL32!RegGetValueW` at `0x180024896`

## string_xrefs

- `0x180024862`: `OverrideConfigMethods`

## pseudocode

```c
bool __fastcall WcnDeviceUsesPushbutton(struct IWCNDevice *a1)
{
  struct IWCNDeviceVtbl *lpVtbl; // rax
  unsigned int Indent; // eax
  __int64 v4; // r10
  char v5; // r11
  int v6; // edx
  struct IWCNDeviceVtbl *v7; // rax
  struct IWCNDeviceVtbl *v8; // rax
  struct IWCNDeviceVtbl *v9; // rax
  char v10; // bl
  int pvData; // [rsp+40h] [rbp-18h] BYREF
  DWORD pcbData[5]; // [rsp+44h] [rbp-14h] BYREF
  unsigned int v14; // [rsp+70h] [rbp+18h] BYREF
  int v15; // [rsp+78h] [rbp+20h] BYREF
  int v16; // [rsp+80h] [rbp+28h] BYREF
  int v17; // [rsp+88h] [rbp+30h] BYREF

  lpVtbl = a1->lpVtbl;
  v14 = 0;
  if ( ((int (__fastcall *)(struct IWCNDevice *, __int64, unsigned int *))lpVtbl->GetIntegerAttribute)(a1, 98, &v14) < 0
    && ((int (__fastcall *)(struct IWCNDevice *, __int64, unsigned int *))a1->lpVtbl->GetIntegerAttribute)(a1, 65, &v14) < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    Indent = (unsigned int)GetIndent(0);
    v6 = 15;
LABEL_26:
    WPP_SF_sd(*(_QWORD *)(v4 + 16), v6, (unsigned int)WPP_f1914741326232246567aea6d76b05ac_Traceguids, Indent, v5);
    return 0;
  }
  v7 = a1->lpVtbl;
  v16 = 0;
  if ( ((int (__fastcall *)(struct IWCNDevice *, __int64, int *))v7->GetIntegerAttribute)(a1, 87, &v16) < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    Indent = (unsigned int)GetIndent(0);
    v6 = 14;
    goto LABEL_26;
  }
  v8 = a1->lpVtbl;
  v17 = 0;
  if ( ((int (__fastcall *)(struct IWCNDevice *, __int64, int *))v8->GetIntegerAttribute)(a1, 89, &v17) < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    Indent = (unsigned int)GetIndent(0);
    v6 = 13;
    goto LABEL_26;
  }
  v9 = a1->lpVtbl;
  v15 = 0;
  if ( ((int (__fastcall *)(struct IWCNDevice *, __int64, int *))v9->GetIntegerAttribute)(a1, 5, &v15) < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 0;
    Indent = (unsigned int)GetIndent(0);
    v6 = 12;
    goto LABEL_26;
  }
  v10 = v15;
  if ( v14 >= 0x20 && v16 == 6 && v17 == 1 )
    v10 = v15 | 0x80;
  pvData = 0;
  pcbData[0] = 4;
  if ( !RegGetValueW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\WCN",
          L"OverrideConfigMethods",
          0x10u,
          0,
          &pvData,
          pcbData)
    && pvData )
  {
    v10 = pvData;
  }
  return v10 < 0;
}

```

## disassembly

```asm
0x180024740  push    rbp
0x180024742  push    rbx
0x180024743  mov     rbp, rsp
0x180024746  sub     rsp, 58h
0x18002474a  mov     rax, [rcx]
0x18002474d  lea     r8, [rbp+arg_0]
0x180024751  mov     edx, 62h ; 'b'
0x180024756  mov     [rbp+arg_0], 0
0x18002475d  mov     rbx, rcx
0x180024760  mov     rax, [rax+30h]
0x180024764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024769  test    eax, eax
0x18002476b  jns     short loc_1800247BF
0x18002476d  mov     rax, [rbx]
0x180024770  lea     r8, [rbp+arg_0]
0x180024774  mov     edx, 41h ; 'A'
0x180024779  mov     rcx, rbx
0x18002477c  mov     rax, [rax+30h]
0x180024780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024785  mov     r11d, eax
0x180024788  test    eax, eax
0x18002478a  jns     short loc_1800247BF
0x18002478c  mov     r10, cs:WPP_GLOBAL_Control
0x180024793  lea     rcx, WPP_GLOBAL_Control
0x18002479a  cmp     r10, rcx
0x18002479d  jz      loc_180024943
0x1800247a3  cmp     byte ptr [r10+19h], 2
0x1800247a8  jb      loc_180024943
0x1800247ae  xor     ecx, ecx; int
0x1800247b0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800247b5  mov     edx, 0Fh
0x1800247ba  jmp     loc_18002492B
0x1800247bf  mov     rax, [rbx]
0x1800247c2  lea     r8, [rbp+arg_10]
0x1800247c6  mov     edx, 57h ; 'W'
0x1800247cb  mov     [rbp+arg_10], 0
0x1800247d2  mov     rcx, rbx
0x1800247d5  mov     rax, [rax+30h]
0x1800247d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247de  mov     r11d, eax
0x1800247e1  test    eax, eax
0x1800247e3  js      loc_180024905
0x1800247e9  mov     rax, [rbx]
0x1800247ec  lea     r8, [rbp+arg_18]
0x1800247f0  mov     edx, 59h ; 'Y'
0x1800247f5  mov     [rbp+arg_18], 0
0x1800247fc  mov     rcx, rbx
0x1800247ff  mov     rax, [rax+30h]
0x180024803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024808  mov     r11d, eax
0x18002480b  test    eax, eax
0x18002480d  js      loc_1800248DD
0x180024813  mov     rax, [rbx]
0x180024816  lea     r8, [rbp+arg_8]
0x18002481a  mov     edx, 5
0x18002481f  mov     [rbp+arg_8], 0
0x180024826  mov     rcx, rbx
0x180024829  mov     rax, [rax+30h]
0x18002482d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024832  mov     r11d, eax
0x180024835  test    eax, eax
0x180024837  js      short loc_1800248B5
0x180024839  cmp     [rbp+arg_0], 20h ; ' '
0x18002483d  mov     ebx, [rbp+arg_8]
0x180024840  jb      short loc_180024852
0x180024842  cmp     [rbp+arg_10], 6
0x180024846  jnz     short loc_180024852
0x180024848  cmp     [rbp+arg_18], 1
0x18002484c  jnz     short loc_180024852
0x18002484e  bts     ebx, 7
0x180024852  lea     rax, [rbp+var_14]
0x180024856  mov     [rbp+var_18], 0
0x18002485d  mov     [rsp+58h+pcbData], rax; pcbData
0x180024862  lea     r8, Value; "OverrideConfigMethods"
0x180024869  lea     rax, [rbp+var_18]
0x18002486d  mov     [rbp+var_14], 4
0x180024874  mov     [rsp+58h+pvData], rax; pvData
0x180024879  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180024880  mov     r9d, 10h; dwFlags
0x180024886  mov     [rsp+58h+pdwType], 0; pdwType
0x18002488f  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180024896  call    cs:__imp_RegGetValueW
0x18002489c  test    eax, eax
0x18002489e  jnz     short loc_1800248A8
0x1800248a0  mov     ecx, [rbp+var_18]
0x1800248a3  test    ecx, ecx
0x1800248a5  cmovnz  ebx, ecx
0x1800248a8  shr     ebx, 7
0x1800248ab  and     bl, 1
0x1800248ae  mov     al, bl
0x1800248b0  jmp     loc_180024945
0x1800248b5  mov     r10, cs:WPP_GLOBAL_Control
0x1800248bc  lea     rcx, WPP_GLOBAL_Control
0x1800248c3  cmp     r10, rcx
0x1800248c6  jz      short loc_180024943
0x1800248c8  cmp     byte ptr [r10+19h], 2
0x1800248cd  jb      short loc_180024943
0x1800248cf  xor     ecx, ecx; int
0x1800248d1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800248d6  mov     edx, 0Ch
0x1800248db  jmp     short loc_18002492B
0x1800248dd  mov     r10, cs:WPP_GLOBAL_Control
0x1800248e4  lea     rcx, WPP_GLOBAL_Control
0x1800248eb  cmp     r10, rcx
0x1800248ee  jz      short loc_180024943
0x1800248f0  cmp     byte ptr [r10+19h], 2
0x1800248f5  jb      short loc_180024943
0x1800248f7  xor     ecx, ecx; int
0x1800248f9  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800248fe  mov     edx, 0Dh
0x180024903  jmp     short loc_18002492B
0x180024905  mov     r10, cs:WPP_GLOBAL_Control
0x18002490c  lea     rcx, WPP_GLOBAL_Control
0x180024913  cmp     r10, rcx
0x180024916  jz      short loc_180024943
0x180024918  cmp     byte ptr [r10+19h], 2
0x18002491d  jb      short loc_180024943
0x18002491f  xor     ecx, ecx; int
0x180024921  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180024926  mov     edx, 0Eh
0x18002492b  mov     rcx, [r10+10h]
0x18002492f  lea     r8, WPP_f1914741326232246567aea6d76b05ac_Traceguids
0x180024936  mov     r9, rax
0x180024939  mov     dword ptr [rsp+58h+pdwType], r11d
0x18002493e  call    WPP_SF_sd
0x180024943  xor     al, al
0x180024945  add     rsp, 58h
0x180024949  pop     rbx
0x18002494a  pop     rbp
0x18002494b  retn
```
