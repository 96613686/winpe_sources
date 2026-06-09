# CPhrase::GetXMLErrorInfo(SPSEMANTICERRORINFO *)

- ea: `0x180105680`
- end: `0x1801057a8`
- name: `?GetXMLErrorInfo@CPhrase@@UEAAJPEAUSPSEMANTICERRORINFO@@@Z`
- size: `296`
- prototype: `__int64 __fastcall(CPhrase *__hidden this, struct SPSEMANTICERRORINFO *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18005d5a8`
- `0x180105680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801056a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801056a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801056d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180105787`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180105794`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801056d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180105787`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180105794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180105740`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010574a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180105754`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180105740`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18010574a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180105754`

## pseudocode

```c
__int64 __fastcall CPhrase::GetXMLErrorInfo(CPhrase *this, struct SPSEMANTICERRORINFO *a2)
{
  __int64 v3; // rsi
  unsigned int v4; // ebx
  __int64 v6; // rcx
  CSpDynamicString *v8; // rcx
  WCHAR *v9; // rax
  CSpDynamicString *v10; // rcx
  WCHAR *v11; // rax
  CSpDynamicString *v12; // rcx
  WCHAR *v13; // rax

  v3 = (__int64)this + 16;
  v4 = 0;
  if ( this == (CPhrase *)8 )
    v3 = 8;
  EnterCriticalSection((LPCRITICAL_SECTION)v3);
  if ( a2 )
  {
    *(_OWORD *)&a2->ulLineNumber = 0;
    *(_OWORD *)&a2->pszSource = 0;
    *(_QWORD *)&a2->hrResultCode = 0;
    v6 = *((_QWORD *)this + 34);
    if ( v6 )
    {
      v8 = (CSpDynamicString *)(v6 + 8);
      if ( *(_QWORD *)v8 )
      {
        v9 = CSpDynamicString::Copy(v8);
        a2->pszScriptLine = v9;
        if ( !v9 )
          goto LABEL_12;
      }
      if ( ((v10 = (CSpDynamicString *)(*((_QWORD *)this + 34) + 16LL), !*(_QWORD *)v10)
         || (v11 = CSpDynamicString::Copy(v10), (a2->pszSource = v11) != 0))
        && ((v12 = (CSpDynamicString *)(*((_QWORD *)this + 34) + 24LL), !*(_QWORD *)v12)
         || (v13 = CSpDynamicString::Copy(v12), (a2->pszDescription = v13) != 0)) )
      {
        a2->ulLineNumber = **((_DWORD **)this + 34);
        a2->hrResultCode = *(_DWORD *)(*((_QWORD *)this + 34) + 32LL);
      }
      else
      {
LABEL_12:
        v4 = -2147024882;
        CoTaskMemFree(a2->pszScriptLine);
        CoTaskMemFree(a2->pszSource);
        CoTaskMemFree(a2->pszDescription);
        *(_OWORD *)&a2->ulLineNumber = 0;
        *(_OWORD *)&a2->pszSource = 0;
        *(_QWORD *)&a2->hrResultCode = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)v3);
      return v4;
    }
    else
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)v3);
      return 1;
    }
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)v3);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180105680  push    rbx
0x180105682  push    rbp
0x180105683  push    rsi
0x180105684  push    rdi
0x180105685  sub     rsp, 28h
0x180105689  lea     rax, [rcx-8]
0x18010568d  mov     rbp, rcx
0x180105690  lea     rsi, [rcx+10h]
0x180105694  xor     ebx, ebx
0x180105696  test    rax, rax
0x180105699  mov     ecx, 8
0x18010569e  mov     rdi, rdx
0x1801056a1  cmovz   rsi, rcx
0x1801056a5  mov     rcx, rsi; lpCriticalSection
0x1801056a8  call    cs:__imp_EnterCriticalSection
0x1801056ae  test    rdi, rdi
0x1801056b1  jz      loc_180105791
0x1801056b7  xorps   xmm0, xmm0
0x1801056ba  xor     eax, eax
0x1801056bc  movups  xmmword ptr [rdi], xmm0
0x1801056bf  movups  xmmword ptr [rdi+10h], xmm0
0x1801056c3  mov     [rdi+20h], rax
0x1801056c7  mov     rcx, [rbp+110h]
0x1801056ce  test    rcx, rcx
0x1801056d1  jnz     short loc_1801056E4
0x1801056d3  mov     rcx, rsi; lpCriticalSection
0x1801056d6  call    cs:__imp_LeaveCriticalSection
0x1801056dc  lea     eax, [rbx+1]
0x1801056df  jmp     loc_18010579F
0x1801056e4  add     rcx, 8; this
0x1801056e8  cmp     [rcx], rbx
0x1801056eb  jz      short loc_1801056FB
0x1801056ed  call    ?Copy@CSpDynamicString@@QEBAPEAGXZ; CSpDynamicString::Copy(void)
0x1801056f2  mov     [rdi+8], rax
0x1801056f6  test    rax, rax
0x1801056f9  jz      short loc_180105737
0x1801056fb  mov     rcx, [rbp+110h]
0x180105702  add     rcx, 10h; this
0x180105706  cmp     [rcx], rbx
0x180105709  jz      short loc_180105719
0x18010570b  call    ?Copy@CSpDynamicString@@QEBAPEAGXZ; CSpDynamicString::Copy(void)
0x180105710  mov     [rdi+10h], rax
0x180105714  test    rax, rax
0x180105717  jz      short loc_180105737
0x180105719  mov     rcx, [rbp+110h]
0x180105720  add     rcx, 18h; this
0x180105724  cmp     [rcx], rbx
0x180105727  jz      short loc_18010576C
0x180105729  call    ?Copy@CSpDynamicString@@QEBAPEAGXZ; CSpDynamicString::Copy(void)
0x18010572e  mov     [rdi+18h], rax
0x180105732  test    rax, rax
0x180105735  jnz     short loc_18010576C
0x180105737  mov     rcx, [rdi+8]; pv
0x18010573b  mov     ebx, 8007000Eh
0x180105740  call    cs:__imp_CoTaskMemFree
0x180105746  mov     rcx, [rdi+10h]; pv
0x18010574a  call    cs:__imp_CoTaskMemFree
0x180105750  mov     rcx, [rdi+18h]; pv
0x180105754  call    cs:__imp_CoTaskMemFree
0x18010575a  xorps   xmm0, xmm0
0x18010575d  xor     eax, eax
0x18010575f  movups  xmmword ptr [rdi], xmm0
0x180105762  movups  xmmword ptr [rdi+10h], xmm0
0x180105766  mov     [rdi+20h], rax
0x18010576a  jmp     short loc_180105784
0x18010576c  mov     rcx, [rbp+110h]
0x180105773  mov     edx, [rcx]
0x180105775  mov     [rdi], edx
0x180105777  mov     rcx, [rbp+110h]
0x18010577e  mov     edx, [rcx+20h]
0x180105781  mov     [rdi+20h], edx
0x180105784  mov     rcx, rsi; lpCriticalSection
0x180105787  call    cs:__imp_LeaveCriticalSection
0x18010578d  mov     eax, ebx
0x18010578f  jmp     short loc_18010579F
0x180105791  mov     rcx, rsi; lpCriticalSection
0x180105794  call    cs:__imp_LeaveCriticalSection
0x18010579a  mov     eax, 80070057h
0x18010579f  add     rsp, 28h
0x1801057a3  pop     rdi
0x1801057a4  pop     rsi
0x1801057a5  pop     rbp
0x1801057a6  pop     rbx
0x1801057a7  retn
```
