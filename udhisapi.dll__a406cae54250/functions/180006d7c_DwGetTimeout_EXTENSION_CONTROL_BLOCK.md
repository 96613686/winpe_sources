# DwGetTimeout(_EXTENSION_CONTROL_BLOCK *)

- ea: `0x180006d7c`
- end: `0x180006e2e`
- name: `?DwGetTimeout@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006f64`
- `0x180007310`

## callees

- `0x1800024c4`
- `0x1800025e8`
- `0x180006d7c`
- `0x180007938`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006de5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006de5`

## pseudocode

```c
__int64 __fastcall DwGetTimeout(struct _EXTENSION_CONTROL_BLOCK *a1)
{
  unsigned int v1; // ebx
  void *Block; // [rsp+38h] [rbp+10h] BYREF

  Block = 0;
  if ( (unsigned int)DwQueryHeader(a1, "HTTP_TIMEOUT", (char **)&Block) )
  {
    v1 = 21600;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, 21600);
  }
  else
  {
    v1 = DwParseTime((const char *)Block);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids, v1);
    free(Block);
  }
  return v1;
}

```

## disassembly

```asm
0x180006d7c  push    rbx
0x180006d7e  sub     rsp, 20h
0x180006d82  lea     r8, [rsp+28h+Block]; char **
0x180006d87  mov     [rsp+28h+Block], 0
0x180006d90  lea     rdx, aHttpTimeout; "HTTP_TIMEOUT"
0x180006d97  call    ?DwQueryHeader@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@PEBDPEAPEAD@Z; DwQueryHeader(_EXTENSION_CONTROL_BLOCK *,char const *,char * *)
0x180006d9c  test    eax, eax
0x180006d9e  jnz     short loc_180006DED
0x180006da0  mov     rcx, [rsp+28h+Block]; String1
0x180006da5  call    ?DwParseTime@@YAKPEBD@Z; DwParseTime(char const *)
0x180006daa  mov     ebx, eax
0x180006dac  mov     rcx, cs:WPP_GLOBAL_Control
0x180006db3  lea     rax, WPP_GLOBAL_Control
0x180006dba  cmp     rcx, rax
0x180006dbd  jz      short loc_180006DE0
0x180006dbf  test    dword ptr [rcx+1Ch], 800h
0x180006dc6  jz      short loc_180006DE0
0x180006dc8  mov     rcx, [rcx+10h]
0x180006dcc  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x180006dd3  mov     edx, 0Ch
0x180006dd8  mov     r9d, ebx
0x180006ddb  call    WPP_SF_d
0x180006de0  mov     rcx, [rsp+28h+Block]; Block
0x180006de5  call    cs:__imp_free
0x180006deb  jmp     short loc_180006E26
0x180006ded  mov     ebx, 5460h
0x180006df2  mov     rcx, cs:WPP_GLOBAL_Control
0x180006df9  lea     rax, WPP_GLOBAL_Control
0x180006e00  cmp     rcx, rax
0x180006e03  jz      short loc_180006E26
0x180006e05  test    dword ptr [rcx+1Ch], 800h
0x180006e0c  jz      short loc_180006E26
0x180006e0e  mov     rcx, [rcx+10h]
0x180006e12  lea     r8, WPP_604df09e42be3037ea2c3a056a88862f_Traceguids
0x180006e19  mov     edx, 0Dh
0x180006e1e  mov     r9d, ebx
0x180006e21  call    WPP_SF_d
0x180006e26  mov     eax, ebx
0x180006e28  add     rsp, 20h
0x180006e2c  pop     rbx
0x180006e2d  retn
```
