# MatchesRequiredForOpenKeySetOnDefaultContainer(_CARD_STATE *,ulong,uchar *,ushort * *,int *)

- ea: `0x1800344c4`
- end: `0x18003468c`
- name: `?MatchesRequiredForOpenKeySetOnDefaultContainer@@YAKPEAU_CARD_STATE@@KPEAEPEAPEAGPEAH@Z`
- size: `456`
- prototype: `unsigned int __fastcall(struct _CARD_STATE *, unsigned int, unsigned __int8 *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800339ac`

## callees

- `0x180009e82`
- `0x18000a408`
- `0x180011fd8`
- `0x180013734`
- `0x180013ce4`
- `0x18002b140`
- `0x18002f034`
- `0x1800344c4`
- `0x18003c240`

## import_xrefs

- `msvcrt!wcsnlen` at `0x1800345a7`
- `msvcrt!wcsnlen` at `0x1800345a7`

## pseudocode

```c
__int64 __fastcall MatchesRequiredForOpenKeySetOnDefaultContainer(
        struct _CARD_STATE *a1,
        int a2,
        unsigned __int8 *a3,
        unsigned __int16 **a4,
        int *a5)
{
  __int64 v9; // rcx
  unsigned int DefaultContainer; // ebx
  __int64 v11; // rcx
  unsigned __int64 v12; // rdi
  unsigned __int16 *v13; // rax
  __int64 v14; // rcx
  wchar_t Source[48]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(Source, 0, 0x56u);
  WppTraceIndent(v9, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  DefaultContainer = ContainerMapGetDefaultContainer(a1, Source, a3);
  if ( DefaultContainer )
  {
    v11 = 4026531840LL;
    LOBYTE(v11) = (a2 & 0xF0000000) != -268435456;
    if ( ((unsigned __int8)v11 & ((a2 & 0x80u) == 0)) != 0 )
    {
      DefaultContainer = -2146435024;
    }
    else
    {
      *a3 = -1;
      DefaultContainer = 0;
      *a5 = 0;
      *a4 = 0;
    }
  }
  else
  {
    v12 = (unsigned int)wcsnlen(Source, 0x28u) + 1;
    v13 = (unsigned __int16 *)MIDL_user_allocate(2 * v12);
    *a4 = v13;
    if ( v13 )
    {
      StringCchCopyNW(v13, v12, Source, 0x28u);
      *a5 = 1;
    }
    else
    {
      WppTraceIndent(v14, 2u);
      DefaultContainer = 8;
      v11 = (__int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          WPP_pszIndent);
      }
    }
  }
  WppTraceIndent(v11, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      DefaultContainer);
  }
  return DefaultContainer;
}

```

## disassembly

```asm
0x1800344c4  push    rbx
0x1800344c6  push    rsi
0x1800344c7  push    rdi
0x1800344c8  push    r14
0x1800344ca  push    r15
0x1800344cc  sub     rsp, 0A0h
0x1800344d3  mov     rax, cs:__security_cookie
0x1800344da  xor     rax, rsp
0x1800344dd  mov     [rsp+0C8h+var_38], rax
0x1800344e5  mov     r14, [rsp+0C8h+arg_20]
0x1800344ed  mov     esi, edx
0x1800344ef  xor     edx, edx; Val
0x1800344f1  mov     rdi, r8
0x1800344f4  mov     rbx, rcx
0x1800344f7  mov     r15, r9
0x1800344fa  lea     rcx, [rsp+0C8h+Source]; void *
0x1800344ff  lea     r8d, [rdx+56h]; Size
0x180034503  call    memset_0
0x180034508  xor     edx, edx
0x18003450a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18003450f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034516  lea     rax, WPP_GLOBAL_Control
0x18003451d  cmp     rcx, rax
0x180034520  jz      short loc_18003454A
0x180034522  test    byte ptr [rcx+1Ch], 2
0x180034526  jz      short loc_18003454A
0x180034528  cmp     byte ptr [rcx+19h], 5
0x18003452c  jb      short loc_18003454A
0x18003452e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180034535  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x18003453c  mov     rcx, [rcx+10h]
0x180034540  mov     edx, 23h ; '#'
0x180034545  call    WPP_SF_s
0x18003454a  mov     r8, rdi
0x18003454d  lea     rdx, [rsp+0C8h+Source]
0x180034552  mov     rcx, rbx
0x180034555  call    ContainerMapGetDefaultContainer
0x18003455a  mov     ebx, eax
0x18003455c  test    eax, eax
0x18003455e  jz      short loc_18003459B
0x180034560  mov     ecx, 0F0000000h
0x180034565  mov     eax, esi
0x180034567  and     eax, ecx
0x180034569  cmp     eax, ecx
0x18003456b  setnz   cl
0x18003456e  test    sil, 80h
0x180034572  setz    al
0x180034575  test    al, cl
0x180034577  jz      short loc_180034583
0x180034579  mov     ebx, 80100030h
0x18003457e  jmp     loc_180034622
0x180034583  mov     byte ptr [rdi], 0FFh
0x180034586  xor     ebx, ebx
0x180034588  mov     dword ptr [r14], 0
0x18003458f  mov     qword ptr [r15], 0
0x180034596  jmp     loc_180034622
0x18003459b  mov     esi, 28h ; '('
0x1800345a0  lea     rcx, [rsp+0C8h+Source]; Source
0x1800345a5  mov     edx, esi; MaxCount
0x1800345a7  call    cs:__imp_wcsnlen
0x1800345ad  inc     eax
0x1800345af  mov     edi, eax
0x1800345b1  lea     rcx, [rax+rax]; size
0x1800345b5  call    MIDL_user_allocate
0x1800345ba  mov     [r15], rax
0x1800345bd  test    rax, rax
0x1800345c0  jnz     short loc_180034608
0x1800345c2  lea     edx, [rsi-26h]
0x1800345c5  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800345ca  lea     ebx, [rsi-20h]
0x1800345cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800345d4  lea     rdi, WPP_GLOBAL_Control
0x1800345db  cmp     rcx, rdi
0x1800345de  jz      short loc_180034629
0x1800345e0  test    byte ptr [rcx+1Ch], 1
0x1800345e4  jz      short loc_180034629
0x1800345e6  cmp     byte ptr [rcx+19h], 2
0x1800345ea  jb      short loc_180034629
0x1800345ec  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800345f3  lea     edx, [rsi-4]
0x1800345f6  mov     rcx, [rcx+10h]
0x1800345fa  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034601  call    WPP_SF_s
0x180034606  jmp     short loc_180034629
0x180034608  mov     r9, rsi; unsigned __int64
0x18003460b  lea     r8, [rsp+0C8h+Source]; unsigned __int16 *
0x180034610  mov     rdx, rdi; unsigned __int64
0x180034613  mov     rcx, rax; unsigned __int16 *
0x180034616  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003461b  mov     dword ptr [r14], 1
0x180034622  lea     rdi, WPP_GLOBAL_Control
0x180034629  mov     edx, 1
0x18003462e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180034633  mov     rcx, cs:WPP_GLOBAL_Control
0x18003463a  cmp     rcx, rdi
0x18003463d  jz      short loc_18003466B
0x18003463f  test    byte ptr [rcx+1Ch], 2
0x180034643  jz      short loc_18003466B
0x180034645  cmp     byte ptr [rcx+19h], 5
0x180034649  jb      short loc_18003466B
0x18003464b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180034652  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180034659  mov     rcx, [rcx+10h]
0x18003465d  mov     edx, 25h ; '%'
0x180034662  mov     [rsp+0C8h+var_A8], ebx
0x180034666  call    WPP_SF_sd
0x18003466b  mov     eax, ebx
0x18003466d  mov     rcx, [rsp+0C8h+var_38]
0x180034675  xor     rcx, rsp; StackCookie
0x180034678  call    __security_check_cookie
0x18003467d  add     rsp, 0A0h
0x180034684  pop     r15
0x180034686  pop     r14
0x180034688  pop     rdi
0x180034689  pop     rsi
0x18003468a  pop     rbx
0x18003468b  retn
```
