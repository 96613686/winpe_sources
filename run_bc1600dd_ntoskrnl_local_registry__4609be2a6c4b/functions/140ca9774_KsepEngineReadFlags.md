# KsepEngineReadFlags

- ea: `0x140ca9774`
- end: `0x140ca9abb`
- name: `KsepEngineReadFlags`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140c73bf4`

## callees

- `0x1404a42cc`
- `0x1404a4304`
- `0x1404eef34`
- `0x1406191e0`
- `0x1407826fc`
- `0x1408befb0`
- `0x1408bfc54`
- `0x140ca9774`

## string_xrefs

- `0x140ca9935`: `KSE: Error reading compatibility key: status: %08x\n`
- `0x140ca9946`: `KSE: Error reading compatibility key: status: %08x\n`
- `0x140ca98df`: `\Registry\Machine\System\CurrentControlSet\Control\Compatibility`
- `0x140ca97e5`: `minkernel\ntos\kshim\kseregistry.c`
- `0x140ca9800`: `\Registry\Machine\System\CurrentControlSet\Policies\Microsoft\Compatibility`
- `0x140ca99b3`: `KSE: Error reading compatibility value [%ws]: status: %08x\n`
- `0x140ca99cb`: `KSE: Error reading compatibility value [%ws]: status: %08x\n`
- `0x140ca9a83`: `KSE: Engine flags (after registry/group policy): %08x\n`
- `0x140ca9a94`: `KSE: Engine flags (after registry/group policy): %08x\n`
- `0x140ca9a2b`: `KSE: Engine initialized with registry flags: %08x\n`
- `0x140ca9a3c`: `KSE: Engine initialized with registry flags: %08x\n`

## pseudocode

```c
__int64 __fastcall KsepEngineReadFlags(_DWORD *a1)
{
  __int64 v2; // rax
  int v3; // eax
  HANDLE v4; // rdi
  __int64 v5; // rax
  unsigned int v6; // edi
  __int64 v7; // rax
  int DWORD; // eax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  HANDLE KeyHandle; // [rsp+78h] [rbp+50h] BYREF

  KeyHandle = 0;
  if ( !a1 )
  {
    v2 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    dword_140EFE0E4[2 * v2] = -1073740768;
    KsepHistoryErrors[2 * v2] = 262242;
    if ( (KsepDebugFlag & 4) != 0 )
      RtlAssert("Engine != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x62u, 0);
  }
  *a1 = 0;
  v3 = KsepRegistryOpenKey(
         L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies\\Microsoft\\Compatibility",
         0,
         &KeyHandle);
  if ( v3 )
  {
    if ( v3 == -1073741772 )
      a1[2] |= 2u;
  }
  else
  {
    v4 = KeyHandle;
    KsepRegistryQueryDWORD(KeyHandle, L"DisableDeviceFlags");
    KsepRegistryQueryDWORD(v4, L"DisableDriverShims");
    v5 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryMessagesIndex, 1u) + 1) & 0x3F;
    HIDWORD(KsepHistoryMessages[v5]) = 0;
    LODWORD(KsepHistoryMessages[v5]) = 262273;
    if ( (KsepDebugFlag & 1) != 0 )
      KsepDebugPrint(0, "KSE: Engine has group policy flags: %08x\n", 0);
    KsepLogInfo(0, "KSE: Engine has group policy flags: %08x\n", 0);
    KsepRegistryCloseKey(v4);
    KeyHandle = 0;
  }
  v6 = KsepRegistryOpenKey(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Compatibility", 0, &KeyHandle);
  if ( v6 == -1073741772 )
  {
    a1[2] |= 1u;
LABEL_12:
    v6 = 0;
    goto LABEL_25;
  }
  if ( (v6 & 0x80000000) == 0 )
  {
    DWORD = KsepRegistryQueryDWORD(KeyHandle, L"DisableFlags");
    v6 = DWORD;
    if ( DWORD == -1073741772 )
      goto LABEL_12;
    if ( DWORD >= 0 )
    {
      *a1 = 0;
      v10 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryMessagesIndex, 1u) + 1) & 0x3F;
      HIDWORD(KsepHistoryMessages[v10]) = 0;
      LODWORD(KsepHistoryMessages[v10]) = 262341;
      if ( (KsepDebugFlag & 1) != 0 )
        KsepDebugPrint(0, "KSE: Engine initialized with registry flags: %08x\n", *a1);
      KsepLogInfo(0, "KSE: Engine initialized with registry flags: %08x\n", *a1);
    }
    else
    {
      v9 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
      dword_140EFE0E4[2 * v9] = v6;
      KsepHistoryErrors[2 * v9] = 262324;
      if ( (KsepDebugFlag & 2) != 0 )
        KsepDebugPrint(0, "KSE: Error reading compatibility value [%ws]: status: %08x\n", L"DisableFlags", v6);
      KsepLogError(0, "KSE: Error reading compatibility value [%ws]: status: %08x\n", L"DisableFlags", v6);
    }
  }
  else
  {
    v7 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    dword_140EFE0E4[2 * v7] = v6;
    KsepHistoryErrors[2 * v7] = 262302;
    if ( (KsepDebugFlag & 2) != 0 )
      KsepDebugPrint(0, "KSE: Error reading compatibility key: status: %08x\n", v6);
    KsepLogError(0, "KSE: Error reading compatibility key: status: %08x\n", v6);
  }
LABEL_25:
  *a1 = *a1;
  v11 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryMessagesIndex, 1u) + 1) & 0x3F;
  HIDWORD(KsepHistoryMessages[v11]) = 0;
  LODWORD(KsepHistoryMessages[v11]) = 262352;
  if ( (KsepDebugFlag & 1) != 0 )
    KsepDebugPrint(0, "KSE: Engine flags (after registry/group policy): %08x\n", *a1);
  KsepLogInfo(0, "KSE: Engine flags (after registry/group policy): %08x\n", *a1);
  KsepRegistryCloseKey(KeyHandle);
  return v6;
}

```

## disassembly

```asm
0x140ca9774  push    rbp
0x140ca9776  push    rbx
0x140ca9777  push    rsi
0x140ca9778  push    rdi
0x140ca9779  push    r12
0x140ca977b  push    r15
0x140ca977d  mov     rbp, rsp
0x140ca9780  sub     rsp, 28h
0x140ca9784  xor     esi, esi
0x140ca9786  mov     [rbp+KeyHandle], 0
0x140ca978e  mov     [rbp+arg_10], 0
0x140ca9795  mov     rbx, rcx
0x140ca9798  lea     r12, cs:140000000h
0x140ca979f  lea     r15d, [rsi+1]
0x140ca97a3  lea     edx, [rsi+4]
0x140ca97a6  test    rcx, rcx
0x140ca97a9  jnz     short loc_140CA97F8
0x140ca97ab  mov     eax, r15d
0x140ca97ae  lock xadd cs:KsepHistoryErrorsIndex, eax
0x140ca97b6  add     eax, r15d
0x140ca97b9  lea     r8d, [rcx+62h]; LineNumber
0x140ca97bd  and     eax, 3Fh
0x140ca97c0  mov     rva dword_140EFE0E4[r12+rax*8], 0C0000420h
0x140ca97cc  mov     rva KsepHistoryErrors[r12+rax*8], 40062h
0x140ca97d8  mov     eax, cs:KsepDebugFlag
0x140ca97de  test    dl, al
0x140ca97e0  jz      short loc_140CA97F8
0x140ca97e2  xor     r9d, r9d; MutableMessage
0x140ca97e5  lea     rdx, aMinkernelNtosK_4; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140ca97ec  lea     rcx, aEngineNull; "Engine != NULL"
0x140ca97f3  call    RtlAssert
0x140ca97f8  lea     r8, [rbp+KeyHandle]
0x140ca97fc  mov     [rbx], esi
0x140ca97fe  xor     edx, edx
0x140ca9800  lea     rcx, aRegistryMachin_138; "\\Registry\\Machine\\System\\CurrentCon"...
0x140ca9807  call    KsepRegistryOpenKey
0x140ca980c  test    eax, eax
0x140ca980e  jnz     loc_140CA98CE
0x140ca9814  mov     rdi, [rbp+KeyHandle]
0x140ca9818  lea     r8, [rbp+arg_0]
0x140ca981c  mov     rcx, rdi; KeyHandle
0x140ca981f  mov     [rbp+arg_0], esi
0x140ca9822  lea     rdx, aDisabledevicef; "DisableDeviceFlags"
0x140ca9829  mov     [rbp+arg_8], esi
0x140ca982c  call    KsepRegistryQueryDWORD
0x140ca9831  test    eax, eax
0x140ca9833  jnz     short loc_140CA9842
0x140ca9835  cmp     [rbp+arg_0], r15d
0x140ca9839  jnz     short loc_140CA9842
0x140ca983b  or      dword ptr [rbx+8], 4
0x140ca983f  lea     esi, [rax+2]
0x140ca9842  lea     r8, [rbp+arg_8]
0x140ca9846  mov     rcx, rdi; KeyHandle
0x140ca9849  lea     rdx, aDisabledrivers; "DisableDriverShims"
0x140ca9850  call    KsepRegistryQueryDWORD
0x140ca9855  test    eax, eax
0x140ca9857  jnz     short loc_140CA9866
0x140ca9859  cmp     [rbp+arg_8], r15d
0x140ca985d  jnz     short loc_140CA9866
0x140ca985f  or      esi, r15d
0x140ca9862  or      dword ptr [rbx+8], 8
0x140ca9866  mov     eax, r15d
0x140ca9869  lock xadd cs:KsepHistoryMessagesIndex, eax
0x140ca9871  add     eax, r15d
0x140ca9874  and     eax, 3Fh
0x140ca9877  mov     dword ptr (rva KsepHistoryMessages+4)[r12+rax*8], 0
0x140ca9883  mov     dword ptr rva KsepHistoryMessages[r12+rax*8], 40081h
0x140ca988f  mov     eax, cs:KsepDebugFlag
0x140ca9895  test    r15b, al
0x140ca9898  jz      short loc_140CA98AB
0x140ca989a  mov     r8d, esi
0x140ca989d  lea     rdx, aKseEngineHasGr; "KSE: Engine has group policy flags: %08"...
0x140ca98a4  xor     ecx, ecx
0x140ca98a6  call    KsepDebugPrint
0x140ca98ab  mov     r8d, esi
0x140ca98ae  lea     rdx, aKseEngineHasGr; "KSE: Engine has group policy flags: %08"...
0x140ca98b5  xor     ecx, ecx
0x140ca98b7  call    KsepLogInfo
0x140ca98bc  mov     rcx, rdi
0x140ca98bf  call    KsepRegistryCloseKey
0x140ca98c4  mov     [rbp+KeyHandle], 0
0x140ca98cc  jmp     short loc_140CA98D9
0x140ca98ce  cmp     eax, 0C0000034h
0x140ca98d3  jnz     short loc_140CA98D9
0x140ca98d5  or      dword ptr [rbx+8], 2
0x140ca98d9  lea     r8, [rbp+KeyHandle]
0x140ca98dd  xor     edx, edx
0x140ca98df  lea     rcx, aRegistryMachin_30; "\\Registry\\Machine\\System\\CurrentCon"...
0x140ca98e6  call    KsepRegistryOpenKey
0x140ca98eb  mov     edi, eax
0x140ca98ed  cmp     eax, 0C0000034h
0x140ca98f2  jnz     short loc_140CA98FF
0x140ca98f4  or      [rbx+8], r15d
0x140ca98f8  xor     edi, edi
0x140ca98fa  jmp     loc_140CA9A4A
0x140ca98ff  test    edi, edi
0x140ca9901  jns     short loc_140CA9959
0x140ca9903  mov     eax, r15d
0x140ca9906  lock xadd cs:KsepHistoryErrorsIndex, eax
0x140ca990e  add     eax, r15d
0x140ca9911  and     eax, 3Fh
0x140ca9914  mov     rva dword_140EFE0E4[r12+rax*8], edi
0x140ca991c  mov     rva KsepHistoryErrors[r12+rax*8], 4009Eh
0x140ca9928  mov     eax, cs:KsepDebugFlag
0x140ca992e  test    al, 2
0x140ca9930  jz      short loc_140CA9943
0x140ca9932  mov     r8d, edi
0x140ca9935  lea     rdx, aKseErrorReadin; "KSE: Error reading compatibility key: s"...
0x140ca993c  xor     ecx, ecx
0x140ca993e  call    KsepDebugPrint
0x140ca9943  mov     r8d, edi
0x140ca9946  lea     rdx, aKseErrorReadin; "KSE: Error reading compatibility key: s"...
0x140ca994d  xor     ecx, ecx
0x140ca994f  call    KsepLogError
0x140ca9954  jmp     loc_140CA9A4A
0x140ca9959  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140ca995d  lea     r8, [rbp+arg_10]
0x140ca9961  lea     rdx, aDisableflags; "DisableFlags"
0x140ca9968  call    KsepRegistryQueryDWORD
0x140ca996d  mov     edi, eax
0x140ca996f  cmp     eax, 0C0000034h
0x140ca9974  jz      short loc_140CA98F8
0x140ca9976  test    eax, eax
0x140ca9978  jns     short loc_140CA99DB
0x140ca997a  mov     eax, r15d
0x140ca997d  lock xadd cs:KsepHistoryErrorsIndex, eax
0x140ca9985  add     eax, r15d
0x140ca9988  and     eax, 3Fh
0x140ca998b  mov     rva dword_140EFE0E4[r12+rax*8], edi
0x140ca9993  mov     rva KsepHistoryErrors[r12+rax*8], 400B4h
0x140ca999f  mov     eax, cs:KsepDebugFlag
0x140ca99a5  test    al, 2
0x140ca99a7  jz      short loc_140CA99C1
0x140ca99a9  mov     r9d, edi
0x140ca99ac  lea     r8, aDisableflags; "DisableFlags"
0x140ca99b3  lea     rdx, aKseErrorReadin_0; "KSE: Error reading compatibility value "...
0x140ca99ba  xor     ecx, ecx
0x140ca99bc  call    KsepDebugPrint
0x140ca99c1  mov     r9d, edi
0x140ca99c4  lea     r8, aDisableflags; "DisableFlags"
0x140ca99cb  lea     rdx, aKseErrorReadin_0; "KSE: Error reading compatibility value "...
0x140ca99d2  xor     ecx, ecx
0x140ca99d4  call    KsepLogError
0x140ca99d9  jmp     short loc_140CA9A4A
0x140ca99db  mov     eax, [rbp+arg_10]
0x140ca99de  and     eax, 3
0x140ca99e1  mov     [rbx], eax
0x140ca99e3  test    r15b, al
0x140ca99e6  jz      short loc_140CA99EC
0x140ca99e8  or      dword ptr [rbx+8], 20h
0x140ca99ec  test    al, 2
0x140ca99ee  jz      short loc_140CA99F4
0x140ca99f0  or      dword ptr [rbx+8], 10h
0x140ca99f4  mov     eax, r15d
0x140ca99f7  lock xadd cs:KsepHistoryMessagesIndex, eax
0x140ca99ff  add     eax, r15d
0x140ca9a02  and     eax, 3Fh
0x140ca9a05  mov     dword ptr (rva KsepHistoryMessages+4)[r12+rax*8], 0
0x140ca9a11  mov     dword ptr rva KsepHistoryMessages[r12+rax*8], 400C5h
0x140ca9a1d  mov     eax, cs:KsepDebugFlag
0x140ca9a23  test    r15b, al
0x140ca9a26  jz      short loc_140CA9A39
0x140ca9a28  mov     r8d, [rbx]
0x140ca9a2b  lea     rdx, aKseEngineIniti; "KSE: Engine initialized with registry f"...
0x140ca9a32  xor     ecx, ecx
0x140ca9a34  call    KsepDebugPrint
0x140ca9a39  mov     r8d, [rbx]
0x140ca9a3c  lea     rdx, aKseEngineIniti; "KSE: Engine initialized with registry f"...
0x140ca9a43  xor     ecx, ecx
0x140ca9a45  call    KsepLogInfo
0x140ca9a4a  or      [rbx], esi
0x140ca9a4c  mov     eax, r15d
0x140ca9a4f  lock xadd cs:KsepHistoryMessagesIndex, eax
0x140ca9a57  add     eax, r15d
0x140ca9a5a  and     eax, 3Fh
0x140ca9a5d  mov     dword ptr (rva KsepHistoryMessages+4)[r12+rax*8], 0
0x140ca9a69  mov     dword ptr rva KsepHistoryMessages[r12+rax*8], 400D0h
0x140ca9a75  mov     eax, cs:KsepDebugFlag
0x140ca9a7b  test    r15b, al
0x140ca9a7e  jz      short loc_140CA9A91
0x140ca9a80  mov     r8d, [rbx]
0x140ca9a83  lea     rdx, aKseEngineFlags; "KSE: Engine flags (after registry/group"...
0x140ca9a8a  xor     ecx, ecx
0x140ca9a8c  call    KsepDebugPrint
0x140ca9a91  mov     r8d, [rbx]
0x140ca9a94  lea     rdx, aKseEngineFlags; "KSE: Engine flags (after registry/group"...
0x140ca9a9b  xor     ecx, ecx
0x140ca9a9d  call    KsepLogInfo
0x140ca9aa2  mov     rcx, [rbp+KeyHandle]
0x140ca9aa6  call    KsepRegistryCloseKey
0x140ca9aab  mov     eax, edi
0x140ca9aad  add     rsp, 28h
0x140ca9ab1  pop     r15
0x140ca9ab3  pop     r12
0x140ca9ab5  pop     rdi
0x140ca9ab6  pop     rsi
0x140ca9ab7  pop     rbx
0x140ca9ab8  pop     rbp
0x140ca9ab9  retn
```
