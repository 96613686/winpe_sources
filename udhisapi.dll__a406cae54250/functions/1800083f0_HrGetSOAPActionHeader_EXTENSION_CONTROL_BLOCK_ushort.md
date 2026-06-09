# HrGetSOAPActionHeader(_EXTENSION_CONTROL_BLOCK *,ushort * *)

- ea: `0x1800083f0`
- end: `0x1800087f7`
- name: `?HrGetSOAPActionHeader@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@PEAPEAG@Z`
- size: `1031`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180006764`

## callees

- `0x180002504`
- `0x180003728`
- `0x1800038ec`
- `0x1800083f0`
- `0x180009a74`
- `0x180009c44`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800086b9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000877e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000879f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800086b9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000877e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000879f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000845b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800085d5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000845b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800085d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008441`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008441`

## pseudocode

```c
__int64 __fastcall HrGetSOAPActionHeader(struct _EXTENSION_CONTROL_BLOCK *a1, unsigned __int16 **a2)
{
  void *v4; // rax
  void *v5; // rdi
  _QWORD *v6; // rcx
  unsigned int Win32Error; // eax
  unsigned int v8; // ebx
  unsigned __int16 *v9; // rsi
  CHAR *i; // r14
  CHAR v11; // al
  __int64 v12; // rbp
  CHAR *v13; // rdx
  size_t v14; // rbx
  CHAR *v15; // rax
  CHAR *v16; // r15
  __int64 v17; // rax
  CHAR *v18; // rcx
  int v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = 0;
  if ( ((unsigned int (__fastcall *)(HCONN, const char *, _QWORD, int *))a1->GetServerVariable)(
         a1->ConnID,
         "SOAPACTION",
         0,
         &v20) )
  {
    v8 = -2147180031;
    goto LABEL_65;
  }
  if ( GetLastError() != 122 )
  {
    v8 = -2147180031;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_66;
    v5 = 0;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
      (unsigned int)"HrGetSOAPActionHeader(): Could not find SOAPAction header",
      1);
    goto LABEL_18;
  }
  v4 = malloc((unsigned int)(v20 + 1));
  v5 = v4;
  if ( v4 )
  {
    if ( ((unsigned int (__fastcall *)(HCONN, const char *, void *, int *))a1->GetServerVariable)(
           a1->ConnID,
           "SOAPACTION",
           v4,
           &v20) )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids, v5);
        v6 = WPP_GLOBAL_Control;
      }
      goto LABEL_21;
    }
    Win32Error = HrFromLastWin32Error();
    v8 = Win32Error;
    if ( Win32Error )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
        (unsigned int)"HrGetSOAPActionHeader(): Failed to get SOAPACTION header",
        Win32Error);
    }
LABEL_18:
    v6 = WPP_GLOBAL_Control;
LABEL_19:
    if ( (v8 & 0x80000000) != 0 )
    {
      v9 = 0;
      if ( !v5 )
      {
LABEL_60:
        if ( (v8 & 0x80000000) == 0 )
        {
          *a2 = v9;
          return v8;
        }
        if ( !v9 )
          goto LABEL_66;
        free(v9);
        goto LABEL_65;
      }
LABEL_59:
      free(v5);
      v6 = WPP_GLOBAL_Control;
      goto LABEL_60;
    }
    if ( v5 )
    {
LABEL_21:
      v9 = 0;
      for ( i = (CHAR *)v5; ; ++i )
      {
        v11 = *i;
        if ( *i != 32 && v11 != 9 )
          break;
      }
      if ( !v11 )
        goto LABEL_52;
      v12 = 0;
      v13 = i;
      do
      {
        if ( v11 == 13 )
          break;
        if ( v11 == 10 )
          break;
        ++v13;
        v12 = (unsigned int)(v12 + 1);
        v11 = *v13;
      }
      while ( *v13 );
      if ( (_DWORD)v12 )
      {
        v14 = (unsigned int)(v12 + 1);
        v15 = (CHAR *)malloc(v14);
        v16 = v15;
        if ( v15 )
        {
          if ( (_DWORD)v12 != -1 )
          {
            if ( v14 <= 0x7FFFFFFF )
            {
              v17 = 2147483646;
              v18 = v16;
              do
              {
                if ( !v17 )
                  break;
                if ( !*i )
                  break;
                *v18++ = *i++;
                --v17;
                --v14;
              }
              while ( v14 );
              v15 = v18 - 1;
              if ( v14 )
                v15 = v18;
            }
            *v15 = 0;
          }
          v16[v12] = 0;
          v9 = WszFromSz(v16);
          if ( v9 )
          {
            v8 = 0;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids, v9);
            }
          }
          else
          {
            v8 = -2147024882;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                50,
                (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
                (unsigned int)"HrGetSOAPActionHeader(): Failed to allocate memory for wide character SOAPAction header",
                14);
          }
          free(v16);
        }
        else
        {
          v8 = -2147024882;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              51,
              (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
              (unsigned int)"HrGetSOAPActionHeader(): Failed to allocate memory for SOAPAction header",
              14);
        }
      }
      else
      {
LABEL_52:
        v8 = -2147467259;
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
          WPP_SF_sd(
            v6[2],
            52,
            (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
            (unsigned int)"HrGetSOAPActionHeader(): SOAPAction header had no value",
            5);
      }
      goto LABEL_59;
    }
    v8 = -2147467259;
    if ( v6 == &WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)v6 + 28) & 1) == 0 )
      goto LABEL_66;
    WPP_SF_sd(
      v6[2],
      53,
      (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
      (unsigned int)"HrGetSOAPActionHeader(): SOAPAction header had no value",
      5);
LABEL_65:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_66;
  }
  v8 = -2147024882;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
      (unsigned int)"HrGetSOAPActionHeader(): Failed to allocate buffer for SOAPACTION headers",
      14);
    goto LABEL_18;
  }
LABEL_66:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    WPP_SF_sd(
      v6[2],
      54,
      (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
      (unsigned int)"HrGetSOAPActionHeader(): Exiting",
      v8);
  return v8;
}

```

## disassembly

```asm
0x1800083f0  mov     rax, rsp
0x1800083f3  mov     [rax+10h], rbx
0x1800083f7  mov     [rax+18h], rbp
0x1800083fb  push    rsi
0x1800083fc  push    rdi
0x1800083fd  push    r12
0x1800083ff  push    r14
0x180008401  push    r15
0x180008403  sub     rsp, 30h
0x180008407  mov     rbx, rcx
0x18000840a  mov     dword ptr [rax+8], 0
0x180008411  mov     rcx, [rcx+8]
0x180008415  lea     r9, [rax+8]
0x180008419  mov     r12, rdx
0x18000841c  xor     r8d, r8d
0x18000841f  lea     rdx, aSoapaction; "SOAPACTION"
0x180008426  mov     rax, [rbx+0A0h]
0x18000842d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008432  lea     r15, WPP_GLOBAL_Control
0x180008439  test    eax, eax
0x18000843b  jnz     loc_1800087A7
0x180008441  call    cs:__imp_GetLastError
0x180008447  mov     esi, 8007000Eh
0x18000844c  cmp     eax, 7Ah ; 'z'
0x18000844f  jnz     loc_18000853A
0x180008455  mov     ecx, [rsp+58h+arg_0]
0x180008459  inc     ecx; Size
0x18000845b  call    cs:__imp_malloc
0x180008461  mov     rdi, rax
0x180008464  test    rax, rax
0x180008467  jz      loc_18000850C
0x18000846d  mov     rcx, [rbx+8]
0x180008471  lea     r9, [rsp+58h+arg_0]
0x180008476  mov     r8, rax
0x180008479  lea     rdx, aSoapaction; "SOAPACTION"
0x180008480  mov     rax, [rbx+0A0h]
0x180008487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000848c  test    eax, eax
0x18000848e  jz      short loc_1800084D1
0x180008490  mov     rcx, cs:WPP_GLOBAL_Control
0x180008497  cmp     rcx, r15
0x18000849a  jz      loc_180008591
0x1800084a0  test    dword ptr [rcx+1Ch], 400h
0x1800084a7  jz      loc_180008591
0x1800084ad  mov     rcx, [rcx+10h]
0x1800084b1  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x1800084b8  mov     edx, 2Dh ; '-'
0x1800084bd  mov     r9, rdi
0x1800084c0  call    WPP_SF_s
0x1800084c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084cc  jmp     loc_180008591
0x1800084d1  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800084d6  mov     ebx, eax
0x1800084d8  test    eax, eax
0x1800084da  jz      loc_180008579
0x1800084e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084e7  cmp     rcx, r15
0x1800084ea  jz      loc_180008580
0x1800084f0  test    byte ptr [rcx+1Ch], 1
0x1800084f4  jz      loc_180008580
0x1800084fa  mov     edx, 2Eh ; '.'
0x1800084ff  mov     [rsp+58h+var_38], eax
0x180008503  lea     r9, aHrgetsoapactio; "HrGetSOAPActionHeader(): Failed to get "...
0x18000850a  jmp     short loc_180008569
0x18000850c  mov     ebx, esi
0x18000850e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008515  cmp     rcx, r15
0x180008518  jz      loc_1800087DE
0x18000851e  test    byte ptr [rcx+1Ch], 1
0x180008522  jz      loc_1800087B3
0x180008528  mov     edx, 2Fh ; '/'
0x18000852d  mov     [rsp+58h+var_38], esi
0x180008531  lea     r9, aHrgetsoapactio_4; "HrGetSOAPActionHeader(): Failed to allo"...
0x180008538  jmp     short loc_180008569
0x18000853a  mov     ebx, 8004A201h
0x18000853f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008546  cmp     rcx, r15
0x180008549  jz      loc_1800087DE
0x18000854f  test    byte ptr [rcx+1Ch], 1
0x180008553  jz      loc_1800087B3
0x180008559  xor     edi, edi
0x18000855b  mov     [rsp+58h+var_38], ebx
0x18000855f  lea     r9, aHrgetsoapactio_1; "HrGetSOAPActionHeader(): Could not find"...
0x180008566  lea     edx, [rdi+30h]
0x180008569  mov     rcx, [rcx+10h]
0x18000856d  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180008574  call    WPP_SF_sd
0x180008579  mov     rcx, cs:WPP_GLOBAL_Control
0x180008580  test    ebx, ebx
0x180008582  js      loc_180008774
0x180008588  test    rdi, rdi
0x18000858b  jz      loc_18000873C
0x180008591  xor     esi, esi
0x180008593  mov     r14, rdi
0x180008596  mov     al, [r14]
0x180008599  cmp     al, 20h ; ' '
0x18000859b  jz      short loc_1800085A1
0x18000859d  cmp     al, 9
0x18000859f  jnz     short loc_1800085A6
0x1800085a1  inc     r14
0x1800085a4  jmp     short loc_180008596
0x1800085a6  test    al, al
0x1800085a8  jz      loc_180008708
0x1800085ae  xor     ebp, ebp
0x1800085b0  mov     rdx, r14
0x1800085b3  cmp     al, 0Dh
0x1800085b5  jz      short loc_1800085C6
0x1800085b7  cmp     al, 0Ah
0x1800085b9  jz      short loc_1800085C6
0x1800085bb  inc     rdx
0x1800085be  inc     ebp
0x1800085c0  mov     al, [rdx]
0x1800085c2  test    al, al
0x1800085c4  jnz     short loc_1800085B3
0x1800085c6  test    ebp, ebp
0x1800085c8  jz      loc_180008708
0x1800085ce  lea     eax, [rbp+1]
0x1800085d1  mov     ecx, eax; Size
0x1800085d3  mov     ebx, eax
0x1800085d5  call    cs:__imp_malloc
0x1800085db  mov     r15, rax
0x1800085de  test    rax, rax
0x1800085e1  jz      loc_1800086CB
0x1800085e7  test    rbx, rbx
0x1800085ea  jz      short loc_180008628
0x1800085ec  cmp     rbx, 7FFFFFFFh
0x1800085f3  ja      short loc_180008625
0x1800085f5  mov     eax, 7FFFFFFEh
0x1800085fa  mov     rcx, r15
0x1800085fd  test    rax, rax
0x180008600  jz      short loc_18000861A
0x180008602  mov     dl, [r14]
0x180008605  test    dl, dl
0x180008607  jz      short loc_18000861A
0x180008609  mov     [rcx], dl
0x18000860b  inc     r14
0x18000860e  inc     rcx
0x180008611  dec     rax
0x180008614  sub     rbx, 1
0x180008618  jnz     short loc_1800085FD
0x18000861a  test    rbx, rbx
0x18000861d  lea     rax, [rcx-1]
0x180008621  cmovnz  rax, rcx
0x180008625  mov     [rax], sil
0x180008628  mov     rcx, r15; lpMultiByteStr
0x18000862b  mov     [rbp+r15+0], sil
0x180008630  call    ?WszFromSz@@YAPEAGPEBD@Z; WszFromSz(char const *)
0x180008635  mov     rsi, rax
0x180008638  test    rax, rax
0x18000863b  jz      short loc_180008673
0x18000863d  xor     ebx, ebx
0x18000863f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008646  lea     rax, WPP_GLOBAL_Control
0x18000864d  cmp     rcx, rax
0x180008650  jz      short loc_1800086B6
0x180008652  test    dword ptr [rcx+1Ch], 400h
0x180008659  jz      short loc_1800086B6
0x18000865b  mov     rcx, [rcx+10h]
0x18000865f  lea     edx, [rbx+31h]
0x180008662  mov     r9, rsi
0x180008665  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x18000866c  call    WPP_SF_S
0x180008671  jmp     short loc_1800086B6
0x180008673  mov     r8d, 8007000Eh
0x180008679  mov     ebx, r8d
0x18000867c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008683  lea     rax, WPP_GLOBAL_Control
0x18000868a  cmp     rcx, rax
0x18000868d  jz      short loc_1800086B6
0x18000868f  test    byte ptr [rcx+1Ch], 1
0x180008693  jz      short loc_1800086B6
0x180008695  mov     rcx, [rcx+10h]
0x180008699  lea     r9, aHrgetsoapactio_2; "HrGetSOAPActionHeader(): Failed to allo"...
0x1800086a0  mov     [rsp+58h+var_38], r8d
0x1800086a5  mov     edx, 32h ; '2'
0x1800086aa  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x1800086b1  call    WPP_SF_sd
0x1800086b6  mov     rcx, r15; Block
0x1800086b9  call    cs:__imp_free
0x1800086bf  lea     r15, WPP_GLOBAL_Control
0x1800086c6  jmp     loc_18000877B
0x1800086cb  mov     r8d, 8007000Eh
0x1800086d1  mov     ebx, r8d
0x1800086d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086db  lea     r15, WPP_GLOBAL_Control
0x1800086e2  cmp     rcx, r15
0x1800086e5  jz      loc_18000877B
0x1800086eb  test    byte ptr [rcx+1Ch], 1
0x1800086ef  jz      loc_18000877B
0x1800086f5  mov     edx, 33h ; '3'
0x1800086fa  mov     [rsp+58h+var_38], r8d
0x1800086ff  lea     r9, aHrgetsoapactio_0; "HrGetSOAPActionHeader(): Failed to allo"...
0x180008706  jmp     short loc_18000872A
0x180008708  mov     eax, 80004005h
0x18000870d  mov     ebx, eax
0x18000870f  cmp     rcx, r15
0x180008712  jz      short loc_18000877B
0x180008714  test    byte ptr [rcx+1Ch], 1
0x180008718  jz      short loc_18000877B
0x18000871a  mov     edx, 34h ; '4'
0x18000871f  mov     [rsp+58h+var_38], eax
0x180008723  lea     r9, aHrgetsoapactio_5; "HrGetSOAPActionHeader(): SOAPAction hea"...
0x18000872a  mov     rcx, [rcx+10h]
0x18000872e  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180008735  call    WPP_SF_sd
0x18000873a  jmp     short loc_18000877B
0x18000873c  mov     eax, 80004005h
0x180008741  mov     ebx, eax
0x180008743  cmp     rcx, r15
0x180008746  jz      loc_1800087DE
0x18000874c  test    byte ptr [rcx+1Ch], 1
0x180008750  jz      short loc_1800087B3
0x180008752  mov     rcx, [rcx+10h]
0x180008756  lea     r9, aHrgetsoapactio_5; "HrGetSOAPActionHeader(): SOAPAction hea"...
0x18000875d  mov     edx, 35h ; '5'
0x180008762  mov     [rsp+58h+var_38], eax
0x180008766  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x18000876d  call    WPP_SF_sd
0x180008772  jmp     short loc_1800087AC
0x180008774  xor     esi, esi
0x180008776  test    rdi, rdi
0x180008779  jz      short loc_18000878B
0x18000877b  mov     rcx, rdi; Block
0x18000877e  call    cs:__imp_free
0x180008784  mov     rcx, cs:WPP_GLOBAL_Control
0x18000878b  test    ebx, ebx
0x18000878d  js      short loc_180008797
0x18000878f  mov     [r12], rsi
0x180008793  jz      short loc_1800087DE
0x180008795  jmp     short loc_1800087B3
0x180008797  test    rsi, rsi
0x18000879a  jz      short loc_1800087B3
0x18000879c  mov     rcx, rsi; Block
0x18000879f  call    cs:__imp_free
0x1800087a5  jmp     short loc_1800087AC
0x1800087a7  mov     ebx, 8004A201h
0x1800087ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087b3  cmp     rcx, r15
0x1800087b6  jz      short loc_1800087DE
0x1800087b8  test    byte ptr [rcx+1Ch], 1
0x1800087bc  jz      short loc_1800087DE
0x1800087be  mov     rcx, [rcx+10h]
0x1800087c2  lea     r9, aHrgetsoapactio_3; "HrGetSOAPActionHeader(): Exiting"
0x1800087c9  mov     edx, 36h ; '6'
0x1800087ce  mov     [rsp+58h+var_38], ebx
0x1800087d2  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x1800087d9  call    WPP_SF_sd
0x1800087de  mov     rbp, [rsp+58h+arg_10]
0x1800087e3  mov     eax, ebx
0x1800087e5  mov     rbx, [rsp+58h+arg_8]
0x1800087ea  add     rsp, 30h
0x1800087ee  pop     r15
0x1800087f0  pop     r14
0x1800087f2  pop     r12
0x1800087f4  pop     rdi
0x1800087f5  pop     rsi
0x1800087f6  retn
```
