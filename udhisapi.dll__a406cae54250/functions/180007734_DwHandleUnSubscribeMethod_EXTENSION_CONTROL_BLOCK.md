# DwHandleUnSubscribeMethod(_EXTENSION_CONTROL_BLOCK *)

- ea: `0x180007734`
- end: `0x180007931`
- name: `?DwHandleUnSubscribeMethod@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@@Z`
- size: `509`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006e40`

## callees

- `0x18000249c`
- `0x1800024c4`
- `0x1800025e8`
- `0x1800026a4`
- `0x1800038ec`
- `0x180007734`
- `0x180007d1c`
- `0x1800080bc`
- `0x180009a74`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007912`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000791b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007912`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000791b`

## string_xrefs

- `0x180007750`: `HTTP_SID`

## pseudocode

```c
__int64 __fastcall DwHandleUnSubscribeMethod(struct _EXTENSION_CONTROL_BLOCK *a1)
{
  unsigned __int16 *v2; // r14
  unsigned int Header; // eax
  CHAR *v4; // r15
  unsigned int v5; // edi
  char *lpszQueryString; // rcx
  int EventingManager; // esi
  unsigned __int16 *v8; // rax
  DWORD v9; // eax
  _QWORD *v10; // rcx
  void *Block; // [rsp+70h] [rbp+8h] BYREF

  Block = 0;
  a1->dwHttpStatusCode = 200;
  v2 = 0;
  Header = DwQueryHeader(a1, "HTTP_SID", (char **)&Block);
  v4 = (CHAR *)Block;
  v5 = Header;
  if ( Header )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids);
    a1->dwHttpStatusCode = 412;
    goto LABEL_26;
  }
  if ( (unsigned int)FIsHeaderPresent(a1, "HTTP_CALLBACK") || (unsigned int)FIsHeaderPresent(a1, "HTTP_NT") )
  {
    EventingManager = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids);
    a1->dwHttpStatusCode = 400;
    v5 = 4;
  }
  else
  {
    lpszQueryString = a1->lpszQueryString;
    Block = 0;
    EventingManager = HrGetEventingManager(lpszQueryString, (struct IUPnPEventingManager **)&Block);
    if ( EventingManager < 0 )
    {
LABEL_16:
      v9 = 412;
      if ( EventingManager != -2147024894 )
        v9 = 500;
      a1->dwHttpStatusCode = v9;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_27;
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_604df09e42be3037ea2c3a056a88862f_Traceguids,
        (unsigned int)"DwHandleUnSubscribeMethod",
        EventingManager);
LABEL_26:
      v10 = WPP_GLOBAL_Control;
LABEL_27:
      v5 = 4;
      goto LABEL_28;
    }
    v8 = WszFromSz(v4);
    v2 = v8;
    if ( !v8 )
    {
      a1->dwHttpStatusCode = 503;
      goto LABEL_26;
    }
    EventingManager = (*(__int64 (__fastcall **)(void *, unsigned __int16 *))(*(_QWORD *)Block + 56LL))(Block, v8);
    if ( EventingManager >= 0 )
      SendSimpleResponse(a1, 0xC8u);
    if ( Block )
      (*(void (__fastcall **)(void *))(*(_QWORD *)Block + 16LL))(Block);
  }
  if ( EventingManager < 0 )
    goto LABEL_16;
  v10 = WPP_GLOBAL_Control;
LABEL_28:
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x800) != 0 )
    WPP_SF_d(v10[2], 42, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, v5);
  free(v2);
  free(v4);
  return v5;
}

```

## disassembly

```asm
0x180007734  push    rbx
0x180007736  push    rsi
0x180007737  push    rdi
0x180007738  push    r12
0x18000773a  push    r14
0x18000773c  push    r15
0x18000773e  sub     rsp, 38h
0x180007742  lea     r8, [rsp+68h+Block]; char **
0x180007747  mov     [rsp+68h+Block], 0
0x180007750  lea     rdx, aHttpSid; "HTTP_SID"
0x180007757  mov     dword ptr [rcx+10h], 0C8h
0x18000775e  mov     rbx, rcx
0x180007761  xor     r14d, r14d
0x180007764  call    ?DwQueryHeader@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@PEBDPEAPEAD@Z; DwQueryHeader(_EXTENSION_CONTROL_BLOCK *,char const *,char * *)
0x180007769  mov     r15, [rsp+68h+Block]
0x18000776e  mov     edi, eax
0x180007770  lea     r12, WPP_GLOBAL_Control
0x180007777  test    eax, eax
0x180007779  jnz     loc_1800078AC
0x18000777f  lea     rdx, aHttpCallback; "HTTP_CALLBACK"
0x180007786  mov     rcx, rbx; struct _EXTENSION_CONTROL_BLOCK *
0x180007789  call    ?FIsHeaderPresent@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBD@Z; FIsHeaderPresent(_EXTENSION_CONTROL_BLOCK *,char const *)
0x18000778e  test    eax, eax
0x180007790  jnz     loc_180007821
0x180007796  lea     rdx, aHttpNt; "HTTP_NT"
0x18000779d  mov     rcx, rbx; struct _EXTENSION_CONTROL_BLOCK *
0x1800077a0  call    ?FIsHeaderPresent@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBD@Z; FIsHeaderPresent(_EXTENSION_CONTROL_BLOCK *,char const *)
0x1800077a5  test    eax, eax
0x1800077a7  jnz     short loc_180007821
0x1800077a9  mov     rcx, [rbx+70h]; char *
0x1800077ad  lea     rdx, [rsp+68h+Block]; struct IUPnPEventingManager **
0x1800077b2  mov     [rsp+68h+Block], r14
0x1800077b7  call    ?HrGetEventingManager@@YAJPEADPEAPEAUIUPnPEventingManager@@@Z; HrGetEventingManager(char *,IUPnPEventingManager * *)
0x1800077bc  mov     esi, eax
0x1800077be  test    eax, eax
0x1800077c0  js      loc_18000785B
0x1800077c6  mov     rcx, r15; lpMultiByteStr
0x1800077c9  call    ?WszFromSz@@YAPEAGPEBD@Z; WszFromSz(char const *)
0x1800077ce  mov     r14, rax
0x1800077d1  test    rax, rax
0x1800077d4  jnz     short loc_1800077E2
0x1800077d6  mov     dword ptr [rbx+10h], 1F7h
0x1800077dd  jmp     loc_1800078DD
0x1800077e2  mov     rcx, [rsp+68h+Block]
0x1800077e7  mov     rdx, r14
0x1800077ea  mov     rax, [rcx]
0x1800077ed  mov     rax, [rax+38h]
0x1800077f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077f6  mov     esi, eax
0x1800077f8  test    eax, eax
0x1800077fa  js      short loc_180007809
0x1800077fc  mov     edx, 0C8h; unsigned int
0x180007801  mov     rcx, rbx; struct _EXTENSION_CONTROL_BLOCK *
0x180007804  call    ?SendSimpleResponse@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; SendSimpleResponse(_EXTENSION_CONTROL_BLOCK *,ulong)
0x180007809  mov     rcx, [rsp+68h+Block]
0x18000780e  test    rcx, rcx
0x180007811  jz      short loc_180007857
0x180007813  mov     rax, [rcx]
0x180007816  mov     rax, [rax+10h]
0x18000781a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000781f  jmp     short loc_180007857
0x180007821  mov     rcx, cs:WPP_GLOBAL_Control
0x180007828  xor     esi, esi
0x18000782a  cmp     rcx, r12
0x18000782d  jz      short loc_18000784B
0x18000782f  test    dword ptr [rcx+1Ch], 800h
0x180007836  jz      short loc_18000784B
0x180007838  mov     rcx, [rcx+10h]
0x18000783c  lea     edx, [rsi+27h]
0x18000783f  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x180007846  call    WPP_SF_
0x18000784b  mov     dword ptr [rbx+10h], 190h
0x180007852  mov     edi, 4
0x180007857  test    esi, esi
0x180007859  jns     short loc_1800078A3
0x18000785b  mov     eax, 19Ch
0x180007860  cmp     esi, 80070002h
0x180007866  lea     ecx, [rax+58h]
0x180007869  cmovnz  eax, ecx
0x18000786c  mov     [rbx+10h], eax
0x18000786f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007876  cmp     rcx, r12
0x180007879  jz      short loc_1800078E4
0x18000787b  test    byte ptr [rcx+1Ch], 1
0x18000787f  jz      short loc_1800078E4
0x180007881  mov     rcx, [rcx+10h]
0x180007885  lea     r9, aDwhandleunsubs; "DwHandleUnSubscribeMethod"
0x18000788c  mov     edx, 29h ; ')'
0x180007891  mov     [rsp+68h+var_48], esi
0x180007895  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x18000789c  call    WPP_SF_sd
0x1800078a1  jmp     short loc_1800078DD
0x1800078a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078aa  jmp     short loc_1800078E9
0x1800078ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078b3  cmp     rcx, r12
0x1800078b6  jz      short loc_1800078D6
0x1800078b8  test    dword ptr [rcx+1Ch], 800h
0x1800078bf  jz      short loc_1800078D6
0x1800078c1  mov     rcx, [rcx+10h]
0x1800078c5  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x1800078cc  mov     edx, 28h ; '('
0x1800078d1  call    WPP_SF_
0x1800078d6  mov     dword ptr [rbx+10h], 19Ch
0x1800078dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078e4  mov     edi, 4
0x1800078e9  cmp     rcx, r12
0x1800078ec  jz      short loc_18000790F
0x1800078ee  test    dword ptr [rcx+1Ch], 800h
0x1800078f5  jz      short loc_18000790F
0x1800078f7  mov     rcx, [rcx+10h]
0x1800078fb  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x180007902  mov     edx, 2Ah ; '*'
0x180007907  mov     r9d, edi
0x18000790a  call    WPP_SF_d
0x18000790f  mov     rcx, r14; Block
0x180007912  call    cs:__imp_free
0x180007918  mov     rcx, r15; Block
0x18000791b  call    cs:__imp_free
0x180007921  mov     eax, edi
0x180007923  add     rsp, 38h
0x180007927  pop     r15
0x180007929  pop     r14
0x18000792b  pop     r12
0x18000792d  pop     rdi
0x18000792e  pop     rsi
0x18000792f  pop     rbx
0x180007930  retn
```
