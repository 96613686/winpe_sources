# CThirdPartyManager::RemoveExternalProductByInstanceId(ushort const *)

- ea: `0x18002006c`
- end: `0x18002018f`
- name: `?RemoveExternalProductByInstanceId@CThirdPartyManager@@QEAAJPEBG@Z`
- size: `291`
- prototype: `int(CThirdPartyManager *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180020018`
- `0x1800382dc`

## callees

- `0x180018b20`
- `0x18002006c`
- `0x1800202e8`
- `0x180023a90`
- `0x180042010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002010b`
- `msvcrt!_wcsicmp` at `0x18002010b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020174`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020174`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800200c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800200c3`

## pseudocode

```c
__int64 __fastcall CThirdPartyManager::RemoveExternalProductByInstanceId(
        CThirdPartyManager *this,
        const unsigned __int16 *a2)
{
  _QWORD *v5; // rcx
  _QWORD *i; // rax
  _QWORD *v7; // rbx
  __int64 Next; // r14
  unsigned int v9; // edi
  _QWORD *v10; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v5 = (_QWORD *)(*((_QWORD *)this + 7) + 56LL);
    for ( i = (_QWORD *)*v5; !i[2]; i = (_QWORD *)*i )
      ;
    v7 = 0;
    if ( i != v5 )
      v7 = i;
    v10 = v7;
    while ( v7 )
    {
      Next = CList<CExternalBase *,CExternalBase *>::GetNext(*((_QWORD *)this + 7), &v10);
      if ( !_wcsicmp(a2, *(const wchar_t **)(Next + 8)) )
      {
        v9 = 0;
        CList<CExternalBase *,CExternalBase *>::RemoveAt(*((_QWORD *)this + 7), v7);
        (**(void (__fastcall ***)(__int64, __int64))Next)(Next, 1);
        goto LABEL_19;
      }
      v7 = v10;
    }
    v9 = -2147467259;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids);
    }
LABEL_19:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    return v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002006c  mov     [rsp+arg_0], rbx
0x180020071  mov     [rsp+arg_10], rbp
0x180020076  push    rsi
0x180020077  push    rdi
0x180020078  push    r14
0x18002007a  sub     rsp, 20h
0x18002007e  mov     rdi, rdx
0x180020081  mov     rsi, rcx
0x180020084  test    rdx, rdx
0x180020087  jnz     short loc_1800200BF
0x180020089  mov     rcx, cs:WPP_GLOBAL_Control
0x180020090  lea     rax, WPP_GLOBAL_Control
0x180020097  cmp     rcx, rax
0x18002009a  jz      short loc_1800200B5
0x18002009c  test    byte ptr [rcx+1Ch], 1
0x1800200a0  jz      short loc_1800200B5
0x1800200a2  mov     rcx, [rcx+10h]
0x1800200a6  lea     edx, [rdi+17h]
0x1800200a9  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x1800200b0  call    WPP_SF_
0x1800200b5  mov     eax, 80070057h
0x1800200ba  jmp     loc_18002017C
0x1800200bf  add     rcx, 10h; lpCriticalSection
0x1800200c3  call    cs:__imp_EnterCriticalSection
0x1800200c9  mov     rcx, [rsi+38h]
0x1800200cd  add     rcx, 38h ; '8'
0x1800200d1  mov     rax, [rcx]
0x1800200d4  jmp     short loc_1800200D9
0x1800200d6  mov     rax, [rax]
0x1800200d9  cmp     qword ptr [rax+10h], 0
0x1800200de  jz      short loc_1800200D6
0x1800200e0  xor     ebx, ebx
0x1800200e2  cmp     rax, rcx
0x1800200e5  cmovnz  rbx, rax
0x1800200e9  mov     [rsp+38h+arg_8], rbx
0x1800200ee  test    rbx, rbx
0x1800200f1  jz      short loc_18002013D
0x1800200f3  mov     rcx, [rsi+38h]
0x1800200f7  lea     rdx, [rsp+38h+arg_8]
0x1800200fc  call    ?GetNext@?$CList@PEAVCExternalBase@@PEAV1@@@QEAAPEAVCExternalBase@@AEAPEAU_CListElement@@@Z; CList<CExternalBase *,CExternalBase *>::GetNext(_CListElement * &)
0x180020101  mov     rcx, rdi; String1
0x180020104  mov     r14, rax
0x180020107  mov     rdx, [rax+8]; String2
0x18002010b  call    cs:__imp__wcsicmp
0x180020111  test    eax, eax
0x180020113  jz      short loc_18002011C
0x180020115  mov     rbx, [rsp+38h+arg_8]
0x18002011a  jmp     short loc_1800200EE
0x18002011c  mov     rcx, [rsi+38h]
0x180020120  mov     rdx, rbx
0x180020123  xor     edi, edi
0x180020125  call    ?RemoveAt@?$CList@PEAVCExternalBase@@PEAV1@@@QEAAXPEAU_CListElement@@@Z; CList<CExternalBase *,CExternalBase *>::RemoveAt(_CListElement *)
0x18002012a  mov     rax, [r14]
0x18002012d  lea     edx, [rdi+1]
0x180020130  mov     rcx, r14
0x180020133  mov     rax, [rax]
0x180020136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002013b  jmp     short loc_180020170
0x18002013d  mov     edi, 80004005h
0x180020142  mov     rcx, cs:WPP_GLOBAL_Control
0x180020149  lea     rax, WPP_GLOBAL_Control
0x180020150  cmp     rcx, rax
0x180020153  jz      short loc_180020170
0x180020155  test    byte ptr [rcx+1Ch], 1
0x180020159  jz      short loc_180020170
0x18002015b  mov     rcx, [rcx+10h]
0x18002015f  lea     r8, WPP_945edad5fd7435d1f807bc12083ac763_Traceguids
0x180020166  mov     edx, 18h
0x18002016b  call    WPP_SF_
0x180020170  lea     rcx, [rsi+10h]; lpCriticalSection
0x180020174  call    cs:__imp_LeaveCriticalSection
0x18002017a  mov     eax, edi
0x18002017c  mov     rbx, [rsp+38h+arg_0]
0x180020181  mov     rbp, [rsp+38h+arg_10]
0x180020186  add     rsp, 20h
0x18002018a  pop     r14
0x18002018c  pop     rdi
0x18002018d  pop     rsi
0x18002018e  retn
```
