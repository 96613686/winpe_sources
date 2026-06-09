# FindCommandInTable

- ea: `0x1800127ac`
- end: `0x180012a47`
- name: `FindCommandInTable`
- size: `667`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180012a50`
- `0x1800146cc`

## callees

- `0x18000a264`
- `0x18000b1f8`
- `0x18000b6d4`
- `0x1800127ac`
- `0x180012cec`
- `0x180012f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800127d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800127d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001280e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001284d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800128be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012909`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800129ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800129f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001280e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001284d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800128be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012909`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800129ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800129f7`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800128ad`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800128ad`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001297c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001297c`

## pseudocode

```c
const WCHAR *__fastcall FindCommandInTable(unsigned int a1, const WCHAR *a2, _DWORD *a3)
{
  __int64 v3; // rbx
  LPCWSTR v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rbp
  char *v9; // r12
  _DWORD *v10; // rbx
  const WCHAR *v11; // rdi
  int v12; // esi
  bool v13; // zf
  int v15; // [rsp+80h] [rbp+8h] BYREF

  v3 = a1;
  v15 = 0;
  EnterCriticalSection(&mciCritSec);
  if ( (unsigned int)v3 >= number_of_command_tables )
  {
    if ( (_DWORD)v3 )
    {
      LeaveCriticalSection(&mciCritSec);
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids,
          (unsigned int)v3);
      }
      return 0;
    }
    if ( mciLoadCommandResource(ghInst, (LPCWSTR)0xC8, 0) == -1 )
    {
      LeaveCriticalSection(&mciCritSec);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        return 0;
      }
      v7 = 35;
      goto LABEL_39;
    }
  }
  v8 = 5 * v3;
  v9 = (char *)LockResource((HGLOBAL)command_tables[5 * v3]);
  if ( !v9 )
  {
    LeaveCriticalSection(&mciCritSec);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return 0;
    }
    v7 = 37;
    goto LABEL_39;
  }
  v10 = (_DWORD *)command_tables[5 * v3 + 3];
  if ( !v10 )
  {
    LeaveCriticalSection(&mciCritSec);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return 0;
    }
    v7 = 38;
LABEL_39:
    WPP_SF_(*((_QWORD *)v6 + 2), v7, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids);
    return 0;
  }
  while ( *v10 != -1 )
  {
    v11 = (const WCHAR *)&v9[*v10];
    mciEatCommandEntry(v11, &v15, 0);
    v12 = v15;
    if ( (unsigned __int64)a2 < 0x10000 )
      v13 = v15 == (unsigned __int16)a2;
    else
      v13 = lstrcmpiW(v11, a2) == 0;
    if ( v13 )
    {
      command_tables[v8 + 4] = (__int64)v9;
      if ( a3 )
        *a3 = v12;
      LeaveCriticalSection(&mciCritSec);
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          (unsigned int)WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids,
          (_DWORD)v11,
          v12);
      }
      return v11;
    }
    ++v10;
  }
  LeaveCriticalSection(&mciCritSec);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v7 = 40;
    goto LABEL_39;
  }
  return 0;
}

```

## disassembly

```asm
0x1800127ac  mov     rax, rsp
0x1800127af  push    rbx
0x1800127b0  push    rbp
0x1800127b1  push    rsi
0x1800127b2  push    rdi
0x1800127b3  push    r12
0x1800127b5  push    r13
0x1800127b7  push    r14
0x1800127b9  push    r15
0x1800127bb  sub     rsp, 38h
0x1800127bf  mov     ebx, ecx
0x1800127c1  lea     r13, mciCritSec
0x1800127c8  mov     rcx, r13; lpCriticalSection
0x1800127cb  mov     dword ptr [rax+8], 0
0x1800127d2  mov     r14, r8
0x1800127d5  mov     r15, rdx
0x1800127d8  call    cs:__imp_EnterCriticalSection
0x1800127de  cmp     ebx, cs:?number_of_command_tables@@3IA; uint number_of_command_tables
0x1800127e4  jb      loc_18001289E
0x1800127ea  test    ebx, ebx
0x1800127ec  jnz     short loc_18001284A
0x1800127ee  mov     rcx, cs:ghInst; hInstance
0x1800127f5  xor     r8d, r8d; wType
0x1800127f8  mov     edx, 0C8h; lpResName
0x1800127fd  call    mciLoadCommandResource
0x180012802  cmp     eax, 0FFFFFFFFh
0x180012805  jnz     loc_18001289E
0x18001280b  mov     rcx, r13; lpCriticalSection
0x18001280e  call    cs:__imp_LeaveCriticalSection
0x180012814  mov     rcx, cs:WPP_GLOBAL_Control
0x18001281b  lea     rax, WPP_GLOBAL_Control
0x180012822  cmp     rcx, rax
0x180012825  jz      loc_180012A34
0x18001282b  test    dword ptr [rcx+1Ch], 400000h
0x180012832  jz      loc_180012A34
0x180012838  cmp     byte ptr [rcx+19h], 1
0x18001283c  jb      loc_180012A34
0x180012842  lea     edx, [rbx+23h]
0x180012845  jmp     loc_180012A24
0x18001284a  mov     rcx, r13; lpCriticalSection
0x18001284d  call    cs:__imp_LeaveCriticalSection
0x180012853  mov     rcx, cs:WPP_GLOBAL_Control
0x18001285a  lea     rax, WPP_GLOBAL_Control
0x180012861  cmp     rcx, rax
0x180012864  jz      loc_180012A34
0x18001286a  test    dword ptr [rcx+1Ch], 400000h
0x180012871  jz      loc_180012A34
0x180012877  cmp     byte ptr [rcx+19h], 1
0x18001287b  jb      loc_180012A34
0x180012881  mov     rcx, [rcx+10h]
0x180012885  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x18001288c  mov     edx, 24h ; '$'
0x180012891  mov     r9d, ebx
0x180012894  call    WPP_SF_d
0x180012899  jmp     loc_180012A34
0x18001289e  lea     rbp, [rbx+rbx*4]
0x1800128a2  lea     rbx, command_tables
0x1800128a9  mov     rcx, [rbx+rbp*8]; hResData
0x1800128ad  call    cs:__imp_LockResource
0x1800128b3  mov     r12, rax
0x1800128b6  test    rax, rax
0x1800128b9  jnz     short loc_1800128FC
0x1800128bb  mov     rcx, r13; lpCriticalSection
0x1800128be  call    cs:__imp_LeaveCriticalSection
0x1800128c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128cb  lea     rax, WPP_GLOBAL_Control
0x1800128d2  cmp     rcx, rax
0x1800128d5  jz      loc_180012A34
0x1800128db  test    dword ptr [rcx+1Ch], 400000h
0x1800128e2  jz      loc_180012A34
0x1800128e8  cmp     byte ptr [rcx+19h], 1
0x1800128ec  jb      loc_180012A34
0x1800128f2  lea     edx, [r12+25h]
0x1800128f7  jmp     loc_180012A24
0x1800128fc  mov     rbx, [rbx+rbp*8+18h]
0x180012901  test    rbx, rbx
0x180012904  jnz     short loc_180012945
0x180012906  mov     rcx, r13; lpCriticalSection
0x180012909  call    cs:__imp_LeaveCriticalSection
0x18001290f  mov     rcx, cs:WPP_GLOBAL_Control
0x180012916  lea     rax, WPP_GLOBAL_Control
0x18001291d  cmp     rcx, rax
0x180012920  jz      loc_180012A34
0x180012926  test    dword ptr [rcx+1Ch], 400000h
0x18001292d  jz      loc_180012A34
0x180012933  cmp     byte ptr [rcx+19h], 1
0x180012937  jb      loc_180012A34
0x18001293d  lea     edx, [rbx+26h]
0x180012940  jmp     loc_180012A24
0x180012945  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180012948  jz      loc_1800129F4
0x18001294e  mov     edi, [rbx]
0x180012950  lea     rdx, [rsp+78h+arg_0]
0x180012958  add     rdi, r12
0x18001295b  xor     r8d, r8d
0x18001295e  mov     rcx, rdi
0x180012961  call    mciEatCommandEntry
0x180012966  mov     esi, [rsp+78h+arg_0]
0x18001296d  cmp     r15, 10000h
0x180012974  jb      short loc_180012986
0x180012976  mov     rdx, r15; lpString2
0x180012979  mov     rcx, rdi; lpString1
0x18001297c  call    cs:__imp_lstrcmpiW
0x180012982  test    eax, eax
0x180012984  jmp     short loc_18001298C
0x180012986  movzx   eax, r15w
0x18001298a  cmp     esi, eax
0x18001298c  jz      short loc_180012994
0x18001298e  add     rbx, 4
0x180012992  jmp     short loc_180012945
0x180012994  lea     rax, command_tables
0x18001299b  mov     [rax+rbp*8+20h], r12
0x1800129a0  test    r14, r14
0x1800129a3  jz      short loc_1800129A8
0x1800129a5  mov     [r14], esi
0x1800129a8  mov     rcx, r13; lpCriticalSection
0x1800129ab  call    cs:__imp_LeaveCriticalSection
0x1800129b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129b8  lea     rax, WPP_GLOBAL_Control
0x1800129bf  cmp     rcx, rax
0x1800129c2  jz      short loc_1800129EF
0x1800129c4  test    dword ptr [rcx+1Ch], 400000h
0x1800129cb  jz      short loc_1800129EF
0x1800129cd  cmp     byte ptr [rcx+19h], 3
0x1800129d1  jb      short loc_1800129EF
0x1800129d3  mov     rcx, [rcx+10h]
0x1800129d7  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x1800129de  mov     edx, 27h ; '''
0x1800129e3  mov     [rsp+78h+var_58], esi
0x1800129e7  mov     r9, rdi
0x1800129ea  call    WPP_SF_Sd
0x1800129ef  mov     rax, rdi
0x1800129f2  jmp     short loc_180012A36
0x1800129f4  mov     rcx, r13; lpCriticalSection
0x1800129f7  call    cs:__imp_LeaveCriticalSection
0x1800129fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a04  lea     rax, WPP_GLOBAL_Control
0x180012a0b  cmp     rcx, rax
0x180012a0e  jz      short loc_180012A34
0x180012a10  test    dword ptr [rcx+1Ch], 400000h
0x180012a17  jz      short loc_180012A34
0x180012a19  cmp     byte ptr [rcx+19h], 3
0x180012a1d  jb      short loc_180012A34
0x180012a1f  mov     edx, 28h ; '('
0x180012a24  mov     rcx, [rcx+10h]
0x180012a28  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x180012a2f  call    WPP_SF_
0x180012a34  xor     eax, eax
0x180012a36  add     rsp, 38h
0x180012a3a  pop     r15
0x180012a3c  pop     r14
0x180012a3e  pop     r13
0x180012a40  pop     r12
0x180012a42  pop     rdi
0x180012a43  pop     rsi
0x180012a44  pop     rbp
0x180012a45  pop     rbx
0x180012a46  retn
```
