# CEngineLocaleHandlerCHX::CreatePronunciationsByCharacter(ushort const *,SPWORDPRONUNCIATIONLIST *)

- ea: `0x1800cea74`
- end: `0x1800cecf5`
- name: `?CreatePronunciationsByCharacter@CEngineLocaleHandlerCHX@@IEAAJPEBGPEAUSPWORDPRONUNCIATIONLIST@@@Z`
- size: `641`
- prototype: `__int64 __fastcall(CEngineLocaleHandlerCHX *__hidden this, const unsigned __int16 *, struct SPWORDPRONUNCIATIONLIST *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ceeb0`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x18001406c`
- `0x1800141c0`
- `0x1800b113c`
- `0x1800c9d10`
- `0x1800cea74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cecbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cecbc`

## pseudocode

```c
__int64 __fastcall CEngineLocaleHandlerCHX::CreatePronunciationsByCharacter(
        WORD *this,
        wchar_t *a2,
        struct SPWORDPRONUNCIATIONLIST *a3)
{
  int v6; // r14d
  int Pronunciations; // ebx
  SPWORDPRONUNCIATION *pFirstWordPronunciation; // rsi
  __int64 v9; // rdi
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rsi
  SPWORDPRONUNCIATION *v13; // r15
  WORD v14; // ax
  __int64 v15; // rax
  struct SPWORDPRONUNCIATION *v16; // rcx
  wchar_t Str[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct SPWORDPRONUNCIATIONLIST pv; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v20[392]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v21[392]; // [rsp+370h] [rbp+270h] BYREF

  memset(&pv, 0, sizeof(pv));
  memset_0(v21, 0, 0x302u);
  memset_0(v20, 0, 0x302u);
  *(_DWORD *)Str = 0;
  if ( !a2 || !*a2 || !a3 )
    return 2147942487LL;
  v6 = 1;
  while ( a2 && *a2 )
  {
    Str[0] = *a2;
    Pronunciations = CEngineLocaleHandler::GetPronunciations((CEngineLocaleHandler *)this, Str, 0x1000u, &pv, 0);
    if ( Pronunciations < 0 )
      goto LABEL_29;
    pFirstWordPronunciation = pv.pFirstWordPronunciation;
    Pronunciations = StringCchCatW(v21, 0x181u, pv.pFirstWordPronunciation->szPronunciation);
    if ( Pronunciations < 0 )
      goto LABEL_29;
    if ( pFirstWordPronunciation->pNextWordPronunciation )
    {
      Pronunciations = StringCchCatW(v20, 0x181u, pFirstWordPronunciation->pNextWordPronunciation->szPronunciation);
      if ( Pronunciations < 0 )
        goto LABEL_29;
      v6 = 0;
    }
    else
    {
      Pronunciations = StringCchCatW(v20, 0x181u, pFirstWordPronunciation->szPronunciation);
      if ( Pronunciations < 0 )
        goto LABEL_29;
    }
    ++a2;
  }
  v9 = -1;
  if ( v6 )
  {
    v10 = 0;
  }
  else
  {
    v11 = -1;
    do
      ++v11;
    while ( v20[v11] );
    v10 = (2 * v11 + 31) & 0xFFFFFFF8;
  }
  v12 = -1;
  do
    ++v12;
  while ( v21[v12] );
  Pronunciations = ReallocSPWORDPRONList(a3, v10 + ((2 * v12 + 31) & 0xFFFFFFF8));
  if ( Pronunciations >= 0 )
  {
    v13 = a3->pFirstWordPronunciation;
    v13->eLexiconType = eLEXTYPE_PRIVATE2;
    v14 = this[20];
    v13->ePartOfSpeech = SPPS_Unknown;
    v13->wPronunciationFlags = 0;
    v13->pNextWordPronunciation = 0;
    v13->LangID = v14;
    Pronunciations = StringCchCopyW(v13->szPronunciation, v12 + 1, v21);
    if ( Pronunciations >= 0 && !v6 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v13->szPronunciation[v15] );
      v16 = (SPWORDPRONUNCIATION *)((char *)v13 + ((2 * v15 + 31) & 0xFFFFFFFFFFFFFFF8uLL));
      v13->pNextWordPronunciation = v16;
      v16->eLexiconType = eLEXTYPE_PRIVATE2;
      v16->LangID = this[20];
      v16->ePartOfSpeech = SPPS_Unknown;
      v16->wPronunciationFlags = 0;
      v16->pNextWordPronunciation = 0;
      do
        ++v9;
      while ( v20[v9] );
      Pronunciations = StringCchCopyW(v16->szPronunciation, v9 + 1, v20);
    }
  }
LABEL_29:
  if ( pv.pvBuffer )
    CoTaskMemFree(pv.pvBuffer);
  return (unsigned int)Pronunciations;
}

```

## disassembly

```asm
0x1800cea74  mov     [rsp-8+arg_8], rbx
0x1800cea79  push    rbp
0x1800cea7a  push    rsi
0x1800cea7b  push    rdi
0x1800cea7c  push    r12
0x1800cea7e  push    r13
0x1800cea80  push    r14
0x1800cea82  push    r15
0x1800cea84  lea     rbp, [rsp-590h]
0x1800cea8c  sub     rsp, 690h
0x1800cea93  mov     rax, cs:__security_cookie
0x1800cea9a  xor     rax, rsp
0x1800cea9d  mov     [rbp+5C0h+var_40], rax
0x1800ceaa4  mov     r13, r8
0x1800ceaa7  mov     rdi, rdx
0x1800ceaaa  mov     r12, rcx
0x1800ceaad  xorps   xmm0, xmm0
0x1800ceab0  xor     eax, eax
0x1800ceab2  lea     rcx, [rbp+5C0h+var_350]; void *
0x1800ceab9  mov     ebx, 302h
0x1800ceabe  mov     [rsp+6C0h+var_670], rax
0x1800ceac3  mov     r8d, ebx; Size
0x1800ceac6  xor     edx, edx; Val
0x1800ceac8  movups  xmmword ptr [rsp+6C0h+pv], xmm0
0x1800ceacd  call    memset_0
0x1800cead2  mov     r8d, ebx; Size
0x1800cead5  lea     rcx, [rsp+6C0h+var_660]; void *
0x1800ceada  xor     edx, edx; Val
0x1800ceadc  call    memset_0
0x1800ceae1  xor     edx, edx
0x1800ceae3  mov     dword ptr [rsp+6C0h+Str], edx
0x1800ceae7  test    rdi, rdi
0x1800ceaea  jz      loc_1800CECC6
0x1800ceaf0  cmp     [rdi], dx
0x1800ceaf3  jz      loc_1800CECC6
0x1800ceaf9  test    r13, r13
0x1800ceafc  jz      loc_1800CECC6
0x1800ceb02  lea     r14d, [rdx+1]
0x1800ceb06  test    rdi, rdi
0x1800ceb09  jz      loc_1800CEBB4
0x1800ceb0f  movzx   eax, word ptr [rdi]
0x1800ceb12  test    ax, ax
0x1800ceb15  jz      loc_1800CEBB4
0x1800ceb1b  mov     [rsp+6C0h+var_6A0], edx; int
0x1800ceb1f  lea     r9, [rsp+6C0h+pv]; struct SPWORDPRONUNCIATIONLIST *
0x1800ceb24  lea     rdx, [rsp+6C0h+Str]; Str
0x1800ceb29  mov     [rsp+6C0h+Str], ax
0x1800ceb2e  mov     r8d, 1000h; unsigned int
0x1800ceb34  mov     rcx, r12; this
0x1800ceb37  call    ?GetPronunciations@CEngineLocaleHandler@@UEAAJPEBGKPEAUSPWORDPRONUNCIATIONLIST@@H@Z; CEngineLocaleHandler::GetPronunciations(ushort const *,ulong,SPWORDPRONUNCIATIONLIST *,int)
0x1800ceb3c  mov     ebx, eax
0x1800ceb3e  test    eax, eax
0x1800ceb40  js      loc_1800CECB2
0x1800ceb46  mov     rsi, [rsp+6C0h+var_670]
0x1800ceb4b  lea     rcx, [rbp+5C0h+var_350]; unsigned __int16 *
0x1800ceb52  mov     edx, 181h; unsigned __int64
0x1800ceb57  lea     r8, [rsi+14h]; unsigned __int16 *
0x1800ceb5b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ceb60  mov     ebx, eax
0x1800ceb62  test    eax, eax
0x1800ceb64  js      loc_1800CECB2
0x1800ceb6a  mov     r8, [rsi]
0x1800ceb6d  lea     rcx, [rsp+6C0h+var_660]; unsigned __int16 *
0x1800ceb72  mov     edx, 181h; unsigned __int64
0x1800ceb77  test    r8, r8
0x1800ceb7a  jz      short loc_1800CEB96
0x1800ceb7c  add     r8, 14h; unsigned __int16 *
0x1800ceb80  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ceb85  xor     edx, edx
0x1800ceb87  mov     ebx, eax
0x1800ceb89  test    eax, eax
0x1800ceb8b  js      loc_1800CECB2
0x1800ceb91  mov     r14d, edx
0x1800ceb94  jmp     short loc_1800CEBAB
0x1800ceb96  lea     r8, [rsi+14h]; unsigned __int16 *
0x1800ceb9a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ceb9f  xor     edx, edx
0x1800ceba1  mov     ebx, eax
0x1800ceba3  test    eax, eax
0x1800ceba5  js      loc_1800CECB2
0x1800cebab  add     rdi, 2
0x1800cebaf  jmp     loc_1800CEB06
0x1800cebb4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800cebb8  test    r14d, r14d
0x1800cebbb  jz      short loc_1800CEBC2
0x1800cebbd  mov     rax, rdx
0x1800cebc0  jmp     short loc_1800CEBDF
0x1800cebc2  lea     rcx, [rsp+6C0h+var_660]
0x1800cebc7  mov     rax, rdi
0x1800cebca  inc     rax
0x1800cebcd  cmp     [rcx+rax*2], dx
0x1800cebd1  jnz     short loc_1800CEBCA
0x1800cebd3  lea     rax, ds:1Fh[rax*2]
0x1800cebdb  and     rax, 0FFFFFFFFFFFFFFF8h
0x1800cebdf  lea     rcx, [rbp+5C0h+var_350]
0x1800cebe6  mov     rsi, rdi
0x1800cebe9  inc     rsi
0x1800cebec  cmp     [rcx+rsi*2], dx
0x1800cebf0  jnz     short loc_1800CEBE9
0x1800cebf2  lea     edx, ds:1Fh[rsi*2]
0x1800cebf9  mov     rcx, r13; struct SPWORDPRONUNCIATIONLIST *
0x1800cebfc  and     edx, 0FFFFFFF8h
0x1800cebff  add     edx, eax; unsigned int
0x1800cec01  call    ?ReallocSPWORDPRONList@@YAJPEAUSPWORDPRONUNCIATIONLIST@@K@Z; ReallocSPWORDPRONList(SPWORDPRONUNCIATIONLIST *,ulong)
0x1800cec06  xor     edx, edx
0x1800cec08  mov     ebx, eax
0x1800cec0a  test    eax, eax
0x1800cec0c  js      loc_1800CECB2
0x1800cec12  mov     r15, [r13+10h]
0x1800cec16  lea     r8, [rbp+5C0h+var_350]; unsigned __int16 *
0x1800cec1d  mov     r13d, 2000h
0x1800cec23  mov     [r15+8], r13d
0x1800cec27  lea     rcx, [r15+14h]; unsigned __int16 *
0x1800cec2b  movzx   eax, word ptr [r12+28h]
0x1800cec31  mov     [r15+10h], edx
0x1800cec35  mov     [r15+0Eh], dx
0x1800cec3a  mov     [r15], rdx
0x1800cec3d  lea     rdx, [rsi+1]; unsigned __int64
0x1800cec41  mov     [r15+0Ch], ax
0x1800cec46  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800cec4b  xor     edx, edx
0x1800cec4d  mov     ebx, eax
0x1800cec4f  test    eax, eax
0x1800cec51  js      short loc_1800CECB2
0x1800cec53  test    r14d, r14d
0x1800cec56  jnz     short loc_1800CECB2
0x1800cec58  mov     rax, rdi
0x1800cec5b  inc     rax
0x1800cec5e  cmp     [r15+rax*2+14h], dx
0x1800cec64  jnz     short loc_1800CEC5B
0x1800cec66  lea     rcx, ds:1Fh[rax*2]
0x1800cec6e  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800cec72  add     rcx, r15
0x1800cec75  mov     [r15], rcx
0x1800cec78  mov     [rcx+8], r13d
0x1800cec7c  movzx   eax, word ptr [r12+28h]
0x1800cec82  mov     [rcx+0Ch], ax
0x1800cec86  lea     rax, [rsp+6C0h+var_660]
0x1800cec8b  mov     [rcx+10h], edx
0x1800cec8e  mov     [rcx+0Eh], dx
0x1800cec92  mov     [rcx], rdx
0x1800cec95  inc     rdi
0x1800cec98  cmp     [rax+rdi*2], dx
0x1800cec9c  jnz     short loc_1800CEC95
0x1800cec9e  lea     rdx, [rdi+1]; unsigned __int64
0x1800ceca2  add     rcx, 14h; unsigned __int16 *
0x1800ceca6  lea     r8, [rsp+6C0h+var_660]; unsigned __int16 *
0x1800cecab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800cecb0  mov     ebx, eax
0x1800cecb2  mov     rcx, [rsp+6C0h+pv+8]; pv
0x1800cecb7  test    rcx, rcx
0x1800cecba  jz      short loc_1800CECC2
0x1800cecbc  call    cs:__imp_CoTaskMemFree
0x1800cecc2  mov     eax, ebx
0x1800cecc4  jmp     short loc_1800CECCB
0x1800cecc6  mov     eax, 80070057h
0x1800ceccb  mov     rcx, [rbp+5C0h+var_40]
0x1800cecd2  xor     rcx, rsp; StackCookie
0x1800cecd5  call    __security_check_cookie
0x1800cecda  mov     rbx, [rsp+6C0h+arg_8]
0x1800cece2  add     rsp, 690h
0x1800cece9  pop     r15
0x1800ceceb  pop     r14
0x1800ceced  pop     r13
0x1800cecef  pop     r12
0x1800cecf1  pop     rdi
0x1800cecf2  pop     rsi
0x1800cecf3  pop     rbp
0x1800cecf4  retn
```
