# SeqUnsubscribeEx

- ea: `0x180005950`
- end: `0x180005d4b`
- name: `SeqUnsubscribeEx`
- size: `1019`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18000e240`

## callees

- `0x180002250`
- `0x180002344`
- `0x180005950`
- `0x180006a54`
- `0x18000720c`
- `0x180008a6c`
- `0x180008abc`
- `0x180009aec`
- `0x180009b7c`
- `0x18000bca4`
- `0x18001dc70`
- `0x180021f44`
- `0x180021ff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005d27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005d27`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027dd9`

## string_xrefs

- `0x180005c71`: `WdsUnsubscribeEx(%s, %s, %d, %d) removed subscription (%s, %d, Callback:%d)`

## pseudocode

```c
__int64 __fastcall SeqUnsubscribeEx(__int64 a1, __int64 a2, const char *a3, int a4, int a5)
{
  int v5; // esi
  __int64 result; // rax
  const char *v10; // r12
  DWORD LastError; // ebx
  int v12; // r15d
  int *v13; // rax
  DWORD v14; // ebx
  int *v15; // rcx
  int ID; // ebx
  DWORD v17; // ebx
  int *v18; // rcx
  __int64 v19; // rdi
  __int64 i; // r12
  __int64 NextListItem; // rax
  __int64 String; // rax
  const wchar_t *v23; // rsi
  __int64 v24; // rbx
  int v25; // edi
  DWORD v26; // r14d
  int Callback; // eax
  __int64 v28; // rcx
  int *v29; // rax
  const char *v30; // [rsp+30h] [rbp-98h]
  unsigned int v31; // [rsp+60h] [rbp-68h]
  int v32; // [rsp+64h] [rbp-64h]
  __int64 v33; // [rsp+70h] [rbp-58h]
  __int128 v34; // [rsp+78h] [rbp-50h] BYREF
  __int64 v35; // [rsp+88h] [rbp-40h]
  LPCWSTR lpModuleName; // [rsp+C8h] [rbp+0h]

  v5 = a4;
  v31 = 0;
  result = IsWorkQueueAccessible((const char *)L"WdsUnsubscribeEx");
  if ( (_DWORD)result )
  {
    v10 = (const char *)(a2 + 44);
    LastError = GetLastError();
    v12 = a5;
    v13 = (int *)ConstructPartialMsgW(0x40000A6u, "WdsUnsubscribeEx(%s, %s, %d, %d) called", v10, a3, v5, a5);
    WdsSetupLogMessageW(
      v13,
      589824,
      (__int64)L"D",
      0,
      0xF8Fu,
      L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
      L"SeqUnsubscribeEx",
      lpModuleName,
      LastError,
      0,
      0);
    pLock(a1);
    if ( !a3 && v5 )
    {
      v14 = GetLastError();
      v15 = (int *)ConstructPartialMsgW(
                     0x30000A7u,
                     "Invalid Major/Minor Event pair given to WdsUnsubscribeEx by %s",
                     v10);
      WdsSetupLogMessageW(
        v15,
        589824,
        (__int64)L"D",
        0,
        0xF95u,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        L"SeqUnsubscribeEx",
        lpModuleName,
        v14,
        0,
        0);
      goto LABEL_28;
    }
    ID = SC_GetID(a1 + 104, a3);
    v32 = ID;
    if ( !ID && a3 )
    {
      v17 = GetLastError();
      v18 = (int *)ConstructPartialMsgW(0x20000A8u, "WdsUnsubscribeEx could not allocate major event");
      WdsSetupLogMessageW(
        v18,
        589824,
        (__int64)L"D",
        0,
        0xF9Du,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        L"SeqUnsubscribeEx",
        lpModuleName,
        v17,
        0,
        0);
LABEL_28:
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
      return v31;
    }
    v34 = 0;
    v35 = 0;
    if ( !(unsigned int)EnumFirstHashTableStringW(&v34) )
      goto LABEL_28;
    v19 = a2;
    while ( !**((_QWORD **)&v34 + 1) )
    {
LABEL_27:
      if ( !(unsigned int)EnumNextHashTableStringW(&v34) )
        goto LABEL_28;
    }
    for ( i = privateGetNonDeletedItem(***((_QWORD ***)&v34 + 1), 1); ; i = NextListItem )
    {
      if ( !i )
        goto LABEL_27;
      NextListItem = GetNextListItem(i);
      v33 = NextListItem;
      if ( *(_QWORD *)(i + 40) == v19 )
      {
        if ( v12 )
        {
          if ( !*(_DWORD *)(i + 28) )
            continue;
        }
        else if ( *(_DWORD *)(i + 28) )
        {
          continue;
        }
        if ( (!ID || ID == *(_DWORD *)(i + 48)) && (!v5 || v5 == *(_DWORD *)(i + 52)) )
        {
          String = SC_GetString(a1 + 104, *(unsigned int *)(i + 48));
          v23 = L"<Null>";
          if ( String )
            v23 = (const wchar_t *)String;
          v24 = *(_QWORD *)(i + 56);
          v25 = *(_DWORD *)(i + 52);
          v26 = GetLastError();
          Callback = pFindCallback(a2, v24);
          v30 = (const char *)v23;
          v5 = a4;
          v29 = (int *)ConstructPartialMsgW(
                         0x40000A9u,
                         "WdsUnsubscribeEx(%s, %s, %d, %d) removed subscription (%s, %d, Callback:%d)",
                         (const char *)(v28 + 44),
                         a3,
                         a4,
                         a5,
                         v30,
                         v25,
                         Callback);
          WdsSetupLogMessageW(
            v29,
            589824,
            (__int64)L"D",
            0,
            0xFCAu,
            L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
            L"SeqUnsubscribeEx",
            lpModuleName,
            v26,
            0,
            0);
          DeleteListItem(*(_QWORD *)i, i);
          v31 = 1;
          ID = v32;
          v12 = a5;
          v19 = a2;
          NextListItem = v33;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005950  mov     rax, rsp
0x180005953  mov     [rax+20h], r9d
0x180005957  mov     [rax+18h], r8
0x18000595b  mov     [rax+10h], rdx
0x18000595f  mov     [rax+8], rcx
0x180005963  push    rbx
0x180005964  push    rsi
0x180005965  push    rdi
0x180005966  push    r12
0x180005968  push    r13
0x18000596a  push    r14
0x18000596c  push    r15
0x18000596e  sub     rsp, 90h
0x180005975  mov     esi, r9d
0x180005978  mov     r14, r8
0x18000597b  mov     rbx, rdx
0x18000597e  mov     r13, rcx
0x180005981  mov     dword ptr [rax-68h], 0
0x180005988  lea     rcx, aWdsunsubscribe_1; "WdsUnsubscribeEx"
0x18000598f  call    IsWorkQueueAccessible
0x180005994  test    eax, eax
0x180005996  jz      loc_180005D37
0x18000599c  mov     rdi, [rsp+0C8h]
0x1800059a4  lea     r12, [rbx+2Ch]
0x1800059a8  call    cs:__imp_GetLastError
0x1800059af  nop     dword ptr [rax+rax+00h]
0x1800059b4  mov     ebx, eax
0x1800059b6  mov     r15d, [rsp+0C8h+arg_20]
0x1800059be  mov     dword ptr [rsp+0C8h+var_A0], r15d
0x1800059c3  mov     [rsp+0C8h+var_A8], esi
0x1800059c7  mov     r9, r14
0x1800059ca  mov     r8, r12
0x1800059cd  lea     rdx, aWdsunsubscribe_2; "WdsUnsubscribeEx(%s, %s, %d, %d) called"
0x1800059d4  mov     ecx, 40000A6h; unsigned int
0x1800059d9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800059de  mov     rcx, rax; int
0x1800059e1  mov     [rsp+0C8h+var_78], 0; int
0x1800059e9  mov     [rsp+0C8h+var_80], 0; __int64
0x1800059f2  mov     [rsp+0C8h+var_88], ebx; int
0x1800059f6  mov     [rsp+0C8h+lpModuleName], rdi; lpModuleName
0x1800059fb  lea     rax, aSequnsubscribe; "SeqUnsubscribeEx"
0x180005a02  mov     [rsp+0C8h+var_98], rax; __int64
0x180005a07  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180005a0e  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 *
0x180005a13  mov     [rsp+0C8h+var_A8], 0F8Fh; int
0x180005a1b  xor     r9d, r9d; int
0x180005a1e  lea     r8, aD_1; "D"
0x180005a25  mov     edx, 90000h; int
0x180005a2a  call    WdsSetupLogMessageW
0x180005a2f  mov     rcx, r13
0x180005a32  call    pLock
0x180005a37  test    r14, r14
0x180005a3a  jnz     short loc_180005AB9
0x180005a3c  test    esi, esi
0x180005a3e  jz      short loc_180005AB9
0x180005a40  mov     rdi, [rsp+0C8h]
0x180005a48  call    cs:__imp_GetLastError
0x180005a4f  nop     dword ptr [rax+rax+00h]
0x180005a54  mov     ebx, eax
0x180005a56  mov     r8, r12
0x180005a59  lea     rdx, aInvalidMajorMi; "Invalid Major/Minor Event pair given to"...
0x180005a60  mov     ecx, 30000A7h; unsigned int
0x180005a65  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005a6a  mov     rcx, rax; int
0x180005a6d  mov     [rsp+0C8h+var_78], r14d; int
0x180005a72  mov     [rsp+0C8h+var_80], r14; __int64
0x180005a77  mov     [rsp+0C8h+var_88], ebx; int
0x180005a7b  mov     [rsp+0C8h+lpModuleName], rdi; lpModuleName
0x180005a80  lea     rax, aSequnsubscribe; "SeqUnsubscribeEx"
0x180005a87  mov     [rsp+0C8h+var_98], rax; __int64
0x180005a8c  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180005a93  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 *
0x180005a98  mov     [rsp+0C8h+var_A8], 0F95h; int
0x180005aa0  xor     r9d, r9d; int
0x180005aa3  lea     r8, aD_1; "D"
0x180005aaa  mov     edx, 90000h; int
0x180005aaf  call    WdsSetupLogMessageW
0x180005ab4  jmp     loc_180005D20
0x180005ab9  lea     rcx, [r13+68h]
0x180005abd  mov     rdx, r14
0x180005ac0  call    SC_GetID
0x180005ac5  mov     ebx, eax
0x180005ac7  mov     [rsp+0C8h+var_64], eax
0x180005acb  test    eax, eax
0x180005acd  jnz     short loc_180005B3D
0x180005acf  test    r14, r14
0x180005ad2  jz      short loc_180005B3D
0x180005ad4  mov     rdi, [rsp+0C8h]
0x180005adc  call    cs:__imp_GetLastError
0x180005ae3  nop     dword ptr [rax+rax+00h]
0x180005ae8  mov     ebx, eax
0x180005aea  lea     rdx, aWdsunsubscribe_3; "WdsUnsubscribeEx could not allocate maj"...
0x180005af1  mov     ecx, 20000A8h; unsigned int
0x180005af6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005afb  mov     rcx, rax
0x180005afe  mov     [rsp+0C8h+var_78], 0
0x180005b06  mov     [rsp+0C8h+var_80], 0
0x180005b0f  mov     [rsp+0C8h+var_88], ebx
0x180005b13  mov     [rsp+0C8h+lpModuleName], rdi
0x180005b18  lea     rax, aSequnsubscribe; "SeqUnsubscribeEx"
0x180005b1f  mov     [rsp+0C8h+var_98], rax
0x180005b24  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180005b2b  mov     [rsp+0C8h+var_A0], rax
0x180005b30  mov     [rsp+0C8h+var_A8], 0F9Dh
0x180005b38  jmp     loc_180005AA0
0x180005b3d  xorps   xmm0, xmm0
0x180005b40  xor     eax, eax
0x180005b42  movups  [rsp+0C8h+var_50], xmm0
0x180005b47  mov     [rsp+0C8h+var_40], rax
0x180005b4f  mov     rdx, [r13+80h]
0x180005b56  lea     rcx, [rsp+0C8h+var_50]
0x180005b5b  call    EnumFirstHashTableStringW
0x180005b60  test    eax, eax
0x180005b62  jz      loc_180005D20
0x180005b68  mov     rdi, [rsp+0C8h+arg_8]
0x180005b70  mov     rax, qword ptr [rsp+0C8h+var_50+8]
0x180005b78  mov     rcx, [rax]
0x180005b7b  test    rcx, rcx
0x180005b7e  jz      loc_180005D0E
0x180005b84  mov     edx, 1
0x180005b89  mov     rcx, [rcx]
0x180005b8c  call    privateGetNonDeletedItem
0x180005b91  mov     r12, rax
0x180005b94  test    r12, r12
0x180005b97  jz      loc_180005D0E
0x180005b9d  mov     rcx, r12
0x180005ba0  call    GetNextListItem
0x180005ba5  mov     [rsp+0C8h+var_58], rax
0x180005baa  cmp     [r12+28h], rdi
0x180005baf  jnz     loc_180005D06
0x180005bb5  test    r15d, r15d
0x180005bb8  jz      short loc_180005BCB
0x180005bba  cmp     dword ptr [r12+1Ch], 0
0x180005bc0  jnz     short loc_180005BD7
0x180005bc2  test    r15d, r15d
0x180005bc5  jnz     loc_180005D06
0x180005bcb  cmp     dword ptr [r12+1Ch], 0
0x180005bd1  jnz     loc_180005D06
0x180005bd7  test    ebx, ebx
0x180005bd9  jz      short loc_180005BE6
0x180005bdb  cmp     ebx, [r12+30h]
0x180005be0  jnz     loc_180005D06
0x180005be6  test    esi, esi
0x180005be8  jz      short loc_180005BF5
0x180005bea  cmp     esi, [r12+34h]
0x180005bef  jnz     loc_180005D06
0x180005bf5  mov     edx, [r12+30h]
0x180005bfa  lea     rcx, [r13+68h]
0x180005bfe  call    SC_GetString
0x180005c03  lea     rsi, aNull; "<Null>"
0x180005c0a  test    rax, rax
0x180005c0d  cmovnz  rsi, rax
0x180005c11  mov     r15, [rsp+0C8h]
0x180005c19  mov     rbx, [r12+38h]
0x180005c1e  mov     edi, [r12+34h]
0x180005c23  call    cs:__imp_GetLastError
0x180005c2a  nop     dword ptr [rax+rax+00h]
0x180005c2f  mov     r14d, eax
0x180005c32  mov     rdx, rbx
0x180005c35  mov     rcx, [rsp+0C8h+arg_8]
0x180005c3d  call    pFindCallback
0x180005c42  lea     r8, [rcx+2Ch]
0x180005c46  mov     [rsp+0C8h+var_88], eax
0x180005c4a  mov     dword ptr [rsp+0C8h+lpModuleName], edi
0x180005c4e  mov     [rsp+0C8h+var_98], rsi
0x180005c53  mov     eax, [rsp+0C8h+arg_20]
0x180005c5a  mov     dword ptr [rsp+0C8h+var_A0], eax
0x180005c5e  mov     esi, [rsp+0C8h+arg_18]
0x180005c65  mov     [rsp+0C8h+var_A8], esi
0x180005c69  mov     r9, [rsp+0C8h+arg_10]
0x180005c71  lea     rdx, aWdsunsubscribe_4; "WdsUnsubscribeEx(%s, %s, %d, %d) remove"...
0x180005c78  mov     ecx, 40000A9h; unsigned int
0x180005c7d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005c82  mov     rcx, rax; int
0x180005c85  mov     [rsp+0C8h+var_78], 0; int
0x180005c8d  mov     [rsp+0C8h+var_80], 0; __int64
0x180005c96  mov     [rsp+0C8h+var_88], r14d; int
0x180005c9b  mov     [rsp+0C8h+lpModuleName], r15; lpModuleName
0x180005ca0  lea     rax, aSequnsubscribe; "SeqUnsubscribeEx"
0x180005ca7  mov     [rsp+0C8h+var_98], rax; __int64
0x180005cac  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180005cb3  mov     [rsp+0C8h+var_A0], rax; unsigned __int16 *
0x180005cb8  mov     [rsp+0C8h+var_A8], 0FCAh; int
0x180005cc0  xor     r9d, r9d; int
0x180005cc3  lea     r8, aD_1; "D"
0x180005cca  mov     edx, 90000h; int
0x180005ccf  call    WdsSetupLogMessageW
0x180005cd4  mov     rdx, r12
0x180005cd7  mov     rcx, [r12]
0x180005cdb  call    DeleteListItem
0x180005ce0  mov     eax, 1
0x180005ce5  mov     [rsp+0C8h+var_68], eax
0x180005ce9  mov     [rsp+0C8h+var_60], eax
0x180005ced  mov     ebx, [rsp+0C8h+var_64]
0x180005cf1  mov     r15d, [rsp+0C8h+arg_20]
0x180005cf9  mov     rdi, [rsp+0C8h+arg_8]
0x180005d01  mov     rax, [rsp+0C8h+var_58]
0x180005d06  mov     r12, rax
0x180005d09  jmp     loc_180005B94
0x180005d0e  lea     rcx, [rsp+0C8h+var_50]
0x180005d13  call    EnumNextHashTableStringW
0x180005d18  test    eax, eax
0x180005d1a  jnz     loc_180005B70
0x180005d20  lea     rcx, [r13+0B8h]; lpCriticalSection
0x180005d27  call    cs:__imp_LeaveCriticalSection
0x180005d2e  nop     dword ptr [rax+rax+00h]
0x180005d33  mov     eax, [rsp+0C8h+var_68]
0x180005d37  add     rsp, 90h
0x180005d3e  pop     r15
0x180005d40  pop     r14
0x180005d42  pop     r13
0x180005d44  pop     r12
0x180005d46  pop     rdi
0x180005d47  pop     rsi
0x180005d48  pop     rbx
0x180005d49  retn
0x180027dbd  push    rbp
0x180027dbf  sub     rsp, 60h
0x180027dc3  mov     rbp, rdx
0x180027dc6  mov     rcx, [rbp+0D0h]
0x180027dcd  add     rcx, 0B8h
0x180027dd4  add     rsp, 60h
0x180027dd8  pop     rbp
0x180027dd9  jmp     cs:__imp_LeaveCriticalSection
```
