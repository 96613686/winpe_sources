# CEngineLocaleHandlerJPN::GetPronunciations(ushort const *,ulong,SPWORDPRONUNCIATIONLIST *,int)

- ea: `0x1800db960`
- end: `0x1800dbb22`
- name: `?GetPronunciations@CEngineLocaleHandlerJPN@@UEAAJPEBGKPEAUSPWORDPRONUNCIATIONLIST@@H@Z`
- size: `450`
- prototype: `__int64 __usercall@<rax>(CEngineLocaleHandlerJPN *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, struct SPWORDPRONUNCIATIONLIST *@<r9>, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800034b0`
- `0x1800040b8`
- `0x18001406c`
- `0x1800141c0`
- `0x1800b113c`
- `0x1800db960`
- `0x1800dbb28`
- `0x180102010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800dba72`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dba86`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dba72`
- `OLEAUT32!__imp_SysFreeString` at `0x1800dba86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbaf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dbaf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEngineLocaleHandlerJPN::GetPronunciations(
        WORD *this,
        wchar_t *a2,
        unsigned int a3,
        struct SPWORDPRONUNCIATIONLIST *a4,
        int a5)
{
  __int16 v6; // r14
  wchar_t *v7; // rdi
  int PronunciationsOneWord; // ebx
  wchar_t v10; // ax
  OLECHAR *v11; // rcx
  __int64 v12; // rdi
  SPWORDPRONUNCIATION *pFirstWordPronunciation; // rcx
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+38h] [rbp-C8h] BYREF
  struct SPWORDPRONUNCIATIONLIST pv; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v18; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[782]; // [rsp+62h] [rbp-9Eh] BYREF

  v6 = a3;
  v7 = a2;
  PronunciationsOneWord = CEngineLocaleHandlerJPN::GetPronunciationsOneWord(
                            (CEngineLocaleHandlerJPN *)this,
                            a2,
                            a3,
                            a4,
                            a5);
  memset(&pv, 0, sizeof(pv));
  if ( PronunciationsOneWord == 1 && (v6 & 0x2000) != 0 )
  {
    v18 = 0;
    memset_0(v19, 0, 0x300u);
    v16 = 0;
    while ( v7 )
    {
      v10 = *v7;
      if ( !*v7 )
        break;
      bstrString = 0;
      LOWORD(v16) = v10;
      PronunciationsOneWord = (*(__int64 (__fastcall **)(WORD *, int *, BSTR *))(*(_QWORD *)this + 208LL))(
                                this,
                                &v16,
                                &bstrString);
      if ( PronunciationsOneWord < 0
        || (PronunciationsOneWord = CEngineLocaleHandlerJPN::GetPronunciationsOneWord(
                                      (CEngineLocaleHandlerJPN *)this,
                                      bstrString,
                                      0x1000u,
                                      &pv,
                                      0),
            PronunciationsOneWord < 0) )
      {
        v11 = bstrString;
LABEL_11:
        SysFreeString(v11);
        goto LABEL_16;
      }
      PronunciationsOneWord = StringCchCatW(&v18, 0x181u, pv.pFirstWordPronunciation->szPronunciation);
      v11 = bstrString;
      if ( PronunciationsOneWord < 0 )
        goto LABEL_11;
      SysFreeString(bstrString);
      ++v7;
    }
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)&v19[2 * v12 - 2] );
    PronunciationsOneWord = ReallocSPWORDPRONList(a4, (2 * v12 + 31) & 0xFFFFFFF8);
    if ( PronunciationsOneWord >= 0 )
    {
      pFirstWordPronunciation = a4->pFirstWordPronunciation;
      pFirstWordPronunciation->eLexiconType = eLEXTYPE_USER;
      pFirstWordPronunciation->LangID = this[20];
      pFirstWordPronunciation->ePartOfSpeech = SPPS_NotOverriden;
      pFirstWordPronunciation->wPronunciationFlags = 0;
      pFirstWordPronunciation->pNextWordPronunciation = 0;
      PronunciationsOneWord = StringCchCopyW(pFirstWordPronunciation->szPronunciation, v12 + 1, &v18);
    }
  }
LABEL_16:
  if ( pv.pvBuffer )
    CoTaskMemFree(pv.pvBuffer);
  return (unsigned int)PronunciationsOneWord;
}

```

## disassembly

```asm
0x1800db960  push    rbp
0x1800db962  push    rbx
0x1800db963  push    rsi
0x1800db964  push    rdi
0x1800db965  push    r12
0x1800db967  push    r14
0x1800db969  push    r15
0x1800db96b  lea     rbp, [rsp-280h]
0x1800db973  sub     rsp, 380h
0x1800db97a  mov     rax, cs:__security_cookie
0x1800db981  xor     rax, rsp
0x1800db984  mov     [rbp+2B0h+var_40], rax
0x1800db98b  mov     r15, r9
0x1800db98e  mov     r14d, r8d
0x1800db991  mov     rdi, rdx
0x1800db994  mov     rsi, rcx
0x1800db997  mov     eax, [rbp+2B0h+arg_20]
0x1800db99d  mov     [rsp+3B0h+var_390], eax; int
0x1800db9a1  call    ?GetPronunciationsOneWord@CEngineLocaleHandlerJPN@@QEAAJPEBGKPEAUSPWORDPRONUNCIATIONLIST@@H@Z; CEngineLocaleHandlerJPN::GetPronunciationsOneWord(ushort const *,ulong,SPWORDPRONUNCIATIONLIST *,int)
0x1800db9a6  mov     ebx, eax
0x1800db9a8  xorps   xmm0, xmm0
0x1800db9ab  xor     eax, eax
0x1800db9ad  movups  xmmword ptr [rsp+3B0h+pv], xmm0
0x1800db9b2  mov     [rsp+3B0h+var_360], rax
0x1800db9b7  xor     r12d, r12d
0x1800db9ba  cmp     ebx, 1
0x1800db9bd  jnz     loc_1800DBAEF
0x1800db9c3  bt      r14d, 0Dh
0x1800db9c8  jnb     loc_1800DBAEF
0x1800db9ce  mov     [rsp+3B0h+var_350], r12w
0x1800db9d4  xor     edx, edx; Val
0x1800db9d6  mov     r8d, 300h; Size
0x1800db9dc  lea     rcx, [rsp+3B0h+var_34E]; void *
0x1800db9e1  call    memset_0
0x1800db9e6  mov     [rsp+3B0h+var_378], r12d
0x1800db9eb  test    rdi, rdi
0x1800db9ee  jz      loc_1800DBA8E
0x1800db9f4  movzx   eax, word ptr [rdi]
0x1800db9f7  test    ax, ax
0x1800db9fa  jz      loc_1800DBA8E
0x1800dba00  mov     [rsp+3B0h+bstrString], r12
0x1800dba05  mov     word ptr [rsp+3B0h+var_378], ax
0x1800dba0a  mov     rax, [rsi]
0x1800dba0d  lea     r8, [rsp+3B0h+bstrString]
0x1800dba12  lea     rdx, [rsp+3B0h+var_378]
0x1800dba17  mov     rcx, rsi
0x1800dba1a  mov     rax, [rax+0D0h]
0x1800dba21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dba26  mov     ebx, eax
0x1800dba28  test    eax, eax
0x1800dba2a  js      short loc_1800DBA81
0x1800dba2c  mov     [rsp+3B0h+var_390], r12d; int
0x1800dba31  lea     r9, [rsp+3B0h+pv]; struct SPWORDPRONUNCIATIONLIST *
0x1800dba36  mov     r8d, 1000h; unsigned int
0x1800dba3c  mov     rdx, [rsp+3B0h+bstrString]; Str
0x1800dba41  mov     rcx, rsi; this
0x1800dba44  call    ?GetPronunciationsOneWord@CEngineLocaleHandlerJPN@@QEAAJPEBGKPEAUSPWORDPRONUNCIATIONLIST@@H@Z; CEngineLocaleHandlerJPN::GetPronunciationsOneWord(ushort const *,ulong,SPWORDPRONUNCIATIONLIST *,int)
0x1800dba49  mov     ebx, eax
0x1800dba4b  test    eax, eax
0x1800dba4d  js      short loc_1800DBA81
0x1800dba4f  mov     r8, [rsp+3B0h+var_360]
0x1800dba54  add     r8, 14h; unsigned __int16 *
0x1800dba58  mov     edx, 181h; unsigned __int64
0x1800dba5d  lea     rcx, [rsp+3B0h+var_350]; unsigned __int16 *
0x1800dba62  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800dba67  mov     ebx, eax
0x1800dba69  mov     rcx, [rsp+3B0h+bstrString]; bstrString
0x1800dba6e  test    eax, eax
0x1800dba70  js      short loc_1800DBA86
0x1800dba72  call    cs:__imp_SysFreeString
0x1800dba78  add     rdi, 2
0x1800dba7c  jmp     loc_1800DB9EB
0x1800dba81  mov     rcx, [rsp+3B0h+bstrString]; bstrString
0x1800dba86  call    cs:__imp_SysFreeString
0x1800dba8c  jmp     short loc_1800DBAEF
0x1800dba8e  lea     rax, [rsp+3B0h+var_350]
0x1800dba93  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800dba97  mov     rdi, r14
0x1800dba9a  inc     rdi
0x1800dba9d  cmp     [rax+rdi*2], r12w
0x1800dbaa2  jnz     short loc_1800DBA9A
0x1800dbaa4  lea     edx, ds:1Fh[rdi*2]
0x1800dbaab  and     edx, 0FFFFFFF8h; unsigned int
0x1800dbaae  mov     rcx, r15; struct SPWORDPRONUNCIATIONLIST *
0x1800dbab1  call    ?ReallocSPWORDPRONList@@YAJPEAUSPWORDPRONUNCIATIONLIST@@K@Z; ReallocSPWORDPRONList(SPWORDPRONUNCIATIONLIST *,ulong)
0x1800dbab6  mov     ebx, eax
0x1800dbab8  test    eax, eax
0x1800dbaba  js      short loc_1800DBAEF
0x1800dbabc  mov     rcx, [r15+10h]
0x1800dbac0  mov     dword ptr [rcx+8], 1
0x1800dbac7  movzx   eax, word ptr [rsi+28h]
0x1800dbacb  mov     [rcx+0Ch], ax
0x1800dbacf  mov     [rcx+10h], r14d
0x1800dbad3  mov     [rcx+0Eh], r12w
0x1800dbad8  mov     [rcx], r12
0x1800dbadb  lea     rdx, [rdi+1]; unsigned __int64
0x1800dbadf  add     rcx, 14h; unsigned __int16 *
0x1800dbae3  lea     r8, [rsp+3B0h+var_350]; unsigned __int16 *
0x1800dbae8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800dbaed  mov     ebx, eax
0x1800dbaef  mov     rcx, [rsp+3B0h+pv+8]; pv
0x1800dbaf4  test    rcx, rcx
0x1800dbaf7  jz      short loc_1800DBAFF
0x1800dbaf9  call    cs:__imp_CoTaskMemFree
0x1800dbaff  mov     eax, ebx
0x1800dbb01  mov     rcx, [rbp+2B0h+var_40]
0x1800dbb08  xor     rcx, rsp; StackCookie
0x1800dbb0b  call    __security_check_cookie
0x1800dbb10  add     rsp, 380h
0x1800dbb17  pop     r15
0x1800dbb19  pop     r14
0x1800dbb1b  pop     r12
0x1800dbb1d  pop     rdi
0x1800dbb1e  pop     rsi
0x1800dbb1f  pop     rbx
0x1800dbb20  pop     rbp
0x1800dbb21  retn
```
