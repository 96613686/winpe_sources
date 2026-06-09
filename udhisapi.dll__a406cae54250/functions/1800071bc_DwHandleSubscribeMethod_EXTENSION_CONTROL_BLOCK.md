# DwHandleSubscribeMethod(_EXTENSION_CONTROL_BLOCK *)

- ea: `0x1800071bc`
- end: `0x180007309`
- name: `?DwHandleSubscribeMethod@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180006e40`

## callees

- `0x18000249c`
- `0x180002504`
- `0x1800025e8`
- `0x180006f64`
- `0x1800071bc`
- `0x180007310`
- `0x180007d1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000723c`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000723c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800072d0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800072d0`

## string_xrefs

- `0x180007246`: `HTTP_SID`

## pseudocode

```c
__int64 __fastcall DwHandleSubscribeMethod(struct _EXTENSION_CONTROL_BLOCK *a1)
{
  int Header; // eax
  unsigned int v3; // ebx
  void *Block; // [rsp+38h] [rbp+10h] BYREF

  Block = 0;
  Header = DwQueryHeader(a1, "HTTP_NT", (char **)&Block);
  if ( Header )
  {
    if ( Header == 1413 )
      return DwHandleResubscribeRequest(a1);
LABEL_21:
    v3 = 4;
    a1->dwHttpStatusCode = 500;
    return v3;
  }
  if ( !Block )
    goto LABEL_21;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, Block);
  if ( (unsigned int)_o__stricmp("upnp:event", Block) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, Block);
    a1->dwHttpStatusCode = 412;
    goto LABEL_17;
  }
  if ( (unsigned int)FIsHeaderPresent(a1, "HTTP_SID") )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids);
    a1->dwHttpStatusCode = 400;
LABEL_17:
    v3 = 4;
    goto LABEL_18;
  }
  v3 = DwHandleSubscribeRequest(a1);
LABEL_18:
  free(Block);
  return v3;
}

```

## disassembly

```asm
0x1800071bc  mov     rax, rsp
0x1800071bf  mov     [rax+8], rbx
0x1800071c3  mov     [rax+18h], rbp
0x1800071c7  push    rdi
0x1800071c8  sub     rsp, 20h
0x1800071cc  lea     r8, [rax+10h]; char **
0x1800071d0  mov     qword ptr [rax+10h], 0
0x1800071d8  lea     rdx, aHttpNt; "HTTP_NT"
0x1800071df  mov     rdi, rcx
0x1800071e2  call    ?DwQueryHeader@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@PEBDPEAPEAD@Z; DwQueryHeader(_EXTENSION_CONTROL_BLOCK *,char const *,char * *)
0x1800071e7  test    eax, eax
0x1800071e9  jnz     loc_1800072D8
0x1800071ef  cmp     [rsp+28h+Block], 0
0x1800071f5  jz      loc_1800072EB
0x1800071fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007202  lea     rbp, WPP_GLOBAL_Control
0x180007209  mov     ebx, 800h
0x18000720e  cmp     rcx, rbp
0x180007211  jz      short loc_180007230
0x180007213  test    [rcx+1Ch], ebx
0x180007216  jz      short loc_180007230
0x180007218  mov     r9, [rsp+28h+Block]
0x18000721d  lea     edx, [rax+24h]
0x180007220  mov     rcx, [rcx+10h]
0x180007224  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x18000722b  call    WPP_SF_s
0x180007230  mov     rdx, [rsp+28h+Block]
0x180007235  lea     rcx, aUpnpEvent; "upnp:event"
0x18000723c  call    cs:__imp__o__stricmp
0x180007242  test    eax, eax
0x180007244  jnz     short loc_180007294
0x180007246  lea     rdx, aHttpSid; "HTTP_SID"
0x18000724d  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x180007250  call    ?FIsHeaderPresent@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBD@Z; FIsHeaderPresent(_EXTENSION_CONTROL_BLOCK *,char const *)
0x180007255  test    eax, eax
0x180007257  jz      short loc_180007288
0x180007259  mov     rcx, cs:WPP_GLOBAL_Control
0x180007260  cmp     rcx, rbp
0x180007263  jz      short loc_18000727F
0x180007265  test    [rcx+1Ch], ebx
0x180007268  jz      short loc_18000727F
0x18000726a  mov     rcx, [rcx+10h]
0x18000726e  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x180007275  mov     edx, 25h ; '%'
0x18000727a  call    WPP_SF_
0x18000727f  mov     dword ptr [rdi+10h], 190h
0x180007286  jmp     short loc_1800072C6
0x180007288  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x18000728b  call    ?DwHandleSubscribeRequest@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@@Z; DwHandleSubscribeRequest(_EXTENSION_CONTROL_BLOCK *)
0x180007290  mov     ebx, eax
0x180007292  jmp     short loc_1800072CB
0x180007294  mov     rcx, cs:WPP_GLOBAL_Control
0x18000729b  cmp     rcx, rbp
0x18000729e  jz      short loc_1800072BF
0x1800072a0  test    [rcx+1Ch], ebx
0x1800072a3  jz      short loc_1800072BF
0x1800072a5  mov     r9, [rsp+28h+Block]
0x1800072aa  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x1800072b1  mov     rcx, [rcx+10h]
0x1800072b5  mov     edx, 26h ; '&'
0x1800072ba  call    WPP_SF_s
0x1800072bf  mov     dword ptr [rdi+10h], 19Ch
0x1800072c6  mov     ebx, 4
0x1800072cb  mov     rcx, [rsp+28h+Block]; Block
0x1800072d0  call    cs:__imp_free
0x1800072d6  jmp     short loc_1800072F7
0x1800072d8  cmp     eax, 585h
0x1800072dd  jnz     short loc_1800072EB
0x1800072df  mov     rcx, rdi; struct _EXTENSION_CONTROL_BLOCK *
0x1800072e2  call    ?DwHandleResubscribeRequest@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@@Z; DwHandleResubscribeRequest(_EXTENSION_CONTROL_BLOCK *)
0x1800072e7  mov     ebx, eax
0x1800072e9  jmp     short loc_1800072F7
0x1800072eb  mov     ebx, 4
0x1800072f0  mov     dword ptr [rdi+10h], 1F4h
0x1800072f7  mov     rbp, [rsp+28h+arg_10]
0x1800072fc  mov     eax, ebx
0x1800072fe  mov     rbx, [rsp+28h+arg_0]
0x180007303  add     rsp, 20h
0x180007307  pop     rdi
0x180007308  retn
```
