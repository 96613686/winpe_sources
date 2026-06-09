# GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)

- ea: `0x180003410`
- end: `0x180003837`
- name: `?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z`
- size: `1063`
- prototype: `__int64 __fastcall(LPCWCH lpString1, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800025b0`

## callees

- `0x180003410`
- `0x180003840`
- `0x180003d70`
- `0x180003f60`
- `0x18000cea0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003624`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003624`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003663`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003705`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003663`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003705`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003655`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003616`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003655`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036f7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000345c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003488`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800034ae`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800034d4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800034fa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000345c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003488`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800034ae`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800034d4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800034fa`

## string_xrefs

- `0x18000377d`: `OneCore\internal\DS\inc\profiles\sid.h`
- `0x1800037b2`: `OneCore\internal\DS\inc\profiles\sid.h`
- `0x180003811`: `OneCore\internal\DS\inc\profiles\sid.h`

## pseudocode

```c
__int64 __fastcall GetProfileListKeyNameFromSid(LPCWCH lpString1, unsigned __int16 **a2, int *a3)
{
  unsigned __int64 v3; // rbx
  int v6; // r15d
  int *v7; // rdx
  int UserProfileListRootKeyName; // esi
  int v9; // eax
  unsigned int v10; // edi
  unsigned __int16 *v11; // rbp
  unsigned __int64 v12; // rax
  unsigned __int16 *v13; // r14
  unsigned __int64 v14; // rdi
  HANDLE v15; // rax
  int v16; // ebx
  HANDLE v17; // rax
  HANDLE v19; // rax
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rcx
  unsigned __int16 *v22; // rdx
  __int64 v23; // rdi
  HANDLE ProcessHeap; // rax
  _WORD *v25; // rax
  _WORD *v26; // r8
  const wchar_t *v27; // rdx
  __int64 v28; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-68h]
  LPVOID lpMem; // [rsp+30h] [rbp-58h] BYREF
  __int64 v31; // [rsp+38h] [rbp-50h]
  __int64 v32; // [rsp+40h] [rbp-48h]
  __int64 v33; // [rsp+48h] [rbp-40h]
  __int64 v34; // [rsp+50h] [rbp-38h]
  __int64 v35; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v3 = -1;
  *a2 = 0;
  lpMem = 0;
  v31 = 0;
  v32 = 0;
  v6 = -2147024882;
  if ( CompareStringOrdinal(lpString1, -1, L"S-1-5-18", -1, 1) == 2
    || CompareStringOrdinal(lpString1, -1, L"S-1-5-19", -1, 1) == 2
    || CompareStringOrdinal(lpString1, -1, L"S-1-5-20", -1, 1) == 2
    || CompareStringOrdinal(lpString1, -1, L"S-1-5-93-2-1", -1, 1) == 2
    || CompareStringOrdinal(lpString1, -1, L"S-1-5-93-2-2", -1, 1) == 2 )
  {
    v23 = 57;
    if ( is_mul_ok(0x39u, 2u) )
    {
      ProcessHeap = GetProcessHeap();
      v25 = HeapAlloc(ProcessHeap, 0, 0x72u);
      v26 = v25;
      if ( v25 )
      {
        v32 = 57;
        v27 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList";
        lpMem = v25;
        v28 = 56;
        *v25 = 0;
        UserProfileListRootKeyName = 0;
        while ( v28 && *v27 )
        {
          *v26++ = *v27++;
          --v28;
          if ( !--v23 )
          {
            --v26;
            break;
          }
        }
        *v26 = 0;
        v31 = 56;
      }
      else
      {
        UserProfileListRootKeyName = -2147024882;
      }
    }
    else
    {
      UserProfileListRootKeyName = -2147024362;
    }
  }
  else
  {
    v31 = -1;
    v32 = -1;
    UserProfileListRootKeyName = GetUserProfileListRootKeyName((unsigned __int16 **)&lpMem, v7);
  }
  if ( UserProfileListRootKeyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"OneCore\\internal\\DS\\inc\\profiles\\sid.h",
      (const char *)(unsigned int)UserProfileListRootKeyName,
      bIgnoreCase);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpMem);
    return (unsigned int)UserProfileListRootKeyName;
  }
  else
  {
    v9 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
           &lpMem,
           L"\\%s",
           lpString1);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"OneCore\\internal\\DS\\inc\\profiles\\sid.h",
        (const char *)(unsigned int)v9,
        bIgnoreCase);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpMem);
      return v10;
    }
    else
    {
      v11 = (unsigned __int16 *)lpMem;
      *a2 = 0;
      if ( v11 )
      {
        v12 = v31;
        v13 = 0;
        v33 = 0;
        v34 = 0;
        v35 = 0;
        if ( v31 == -1 )
        {
          v12 = -1;
          do
            ++v12;
          while ( v11[v12] );
        }
        do
          ++v3;
        while ( v11[v3] );
        if ( v12 == -1 )
        {
          v12 = v3;
        }
        else if ( v12 < v3 )
        {
          v3 = v12;
        }
        v14 = v12 + 1;
        if ( v12 + 1 >= v12 && is_mul_ok(v14, 2u) )
        {
          v19 = GetProcessHeap();
          v20 = (unsigned __int16 *)HeapAlloc(v19, 0, 2 * v14);
          if ( v20 )
          {
            *v20 = 0;
            v13 = v20;
            v6 = 0;
            if ( v14 )
            {
              if ( v14 > 0x7FFFFFFF || v3 > 0x7FFFFFFE )
              {
                *v20 = 0;
              }
              else
              {
                v21 = v11;
                v22 = v20;
                while ( v3 && *v21 )
                {
                  *v22++ = *v21++;
                  --v3;
                  if ( !--v14 )
                  {
                    --v22;
                    break;
                  }
                }
                *v22 = 0;
              }
            }
          }
        }
        else
        {
          v6 = -2147024362;
        }
        if ( v6 >= 0 )
        {
          v16 = v6;
          *a2 = v13;
        }
        else
        {
          if ( v13 )
          {
            v15 = GetProcessHeap();
            HeapFree(v15, 0, v13);
          }
          v16 = v6;
        }
        if ( v16 >= 0 )
        {
          v17 = GetProcessHeap();
          HeapFree(v17, 0, v11);
          return 0;
        }
      }
      else
      {
        v6 = -2147023728;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"OneCore\\internal\\DS\\inc\\profiles\\sid.h",
        (const char *)(unsigned int)v6,
        bIgnoreCase);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&lpMem);
      return (unsigned int)v6;
    }
  }
}

```

## disassembly

```asm
0x180003410  mov     [rsp+arg_8], rbx
0x180003415  mov     [rsp+arg_18], rbp
0x18000341a  push    rsi
0x18000341b  push    rdi
0x18000341c  push    r12
0x18000341e  push    r13
0x180003420  push    r15
0x180003422  sub     rsp, 60h
0x180003426  xor     r13d, r13d
0x180003429  mov     [rsp+88h+bIgnoreCase], 1; int
0x180003431  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180003438  mov     [rdx], r13
0x18000343b  mov     r12, rdx
0x18000343e  mov     [rsp+88h+lpMem], r13
0x180003443  mov     edx, ebx; cchCount1
0x180003445  mov     [rsp+88h+var_50], r13
0x18000344a  mov     r9d, ebx; cchCount2
0x18000344d  mov     [rsp+88h+var_48], r13
0x180003452  lea     r8, String2; "S-1-5-18"
0x180003459  mov     rbp, rcx
0x18000345c  call    cs:__imp_CompareStringOrdinal
0x180003462  mov     r15d, 8007000Eh
0x180003468  cmp     eax, 2
0x18000346b  jz      loc_1800036E2
0x180003471  mov     r9d, ebx; cchCount2
0x180003474  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x18000347c  lea     r8, aS1519; "S-1-5-19"
0x180003483  mov     edx, ebx; cchCount1
0x180003485  mov     rcx, rbp; lpString1
0x180003488  call    cs:__imp_CompareStringOrdinal
0x18000348e  cmp     eax, 2
0x180003491  jz      loc_1800036E2
0x180003497  mov     r9d, ebx; cchCount2
0x18000349a  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x1800034a2  lea     r8, aS1520; "S-1-5-20"
0x1800034a9  mov     edx, ebx; cchCount1
0x1800034ab  mov     rcx, rbp; lpString1
0x1800034ae  call    cs:__imp_CompareStringOrdinal
0x1800034b4  cmp     eax, 2
0x1800034b7  jz      loc_1800036E2
0x1800034bd  mov     r9d, ebx; cchCount2
0x1800034c0  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x1800034c8  lea     r8, aS159321; "S-1-5-93-2-1"
0x1800034cf  mov     edx, ebx; cchCount1
0x1800034d1  mov     rcx, rbp; lpString1
0x1800034d4  call    cs:__imp_CompareStringOrdinal
0x1800034da  cmp     eax, 2
0x1800034dd  jz      loc_1800036E2
0x1800034e3  mov     r9d, ebx; cchCount2
0x1800034e6  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x1800034ee  lea     r8, aS159322; "S-1-5-93-2-2"
0x1800034f5  mov     edx, ebx; cchCount1
0x1800034f7  mov     rcx, rbp; lpString1
0x1800034fa  call    cs:__imp_CompareStringOrdinal
0x180003500  cmp     eax, 2
0x180003503  jz      loc_1800036E2
0x180003509  lea     rcx, [rsp+88h+lpMem]; unsigned __int16 **
0x18000350e  mov     [rsp+88h+var_50], rbx
0x180003513  mov     [rsp+88h+var_48], rbx
0x180003518  call    ?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z; GetUserProfileListRootKeyName(ushort * *,int *)
0x18000351d  mov     esi, eax
0x18000351f  jmp     short loc_180003537
0x180003521  test    rdi, rdi
0x180003524  jz      loc_18000375A
0x18000352a  mov     [r8], r13w
0x18000352e  mov     [rsp+88h+var_50], 38h ; '8'
0x180003537  test    esi, esi
0x180003539  js      loc_180003775
0x18000353f  mov     r8, rbp
0x180003542  lea     rdx, aS_0; "\\%s"
0x180003549  lea     rcx, [rsp+88h+lpMem]
0x18000354e  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180003553  mov     edi, eax
0x180003555  test    eax, eax
0x180003557  js      loc_1800037AA
0x18000355d  mov     rbp, [rsp+88h+lpMem]
0x180003562  mov     [r12], r13
0x180003566  test    rbp, rbp
0x180003569  jz      loc_180003803
0x18000356f  mov     rax, [rsp+88h+var_50]
0x180003574  mov     [rsp+88h+arg_0], r14
0x18000357c  mov     r14, r13
0x18000357f  mov     [rsp+88h+var_40], r13
0x180003584  mov     [rsp+88h+var_38], r13
0x180003589  mov     [rsp+88h+var_30], r13
0x18000358e  cmp     rax, rbx
0x180003591  jnz     short loc_1800035AB
0x180003593  mov     rax, rbx
0x180003596  nop     word ptr [rax+rax+00000000h]
0x1800035a0  inc     rax
0x1800035a3  cmp     [rbp+rax*2+0], r13w
0x1800035a9  jnz     short loc_1800035A0
0x1800035ab  test    rbp, rbp
0x1800035ae  jz      loc_1800037E5
0x1800035b4  inc     rbx
0x1800035b7  cmp     [rbp+rbx*2+0], r13w
0x1800035bd  jnz     short loc_1800035B4
0x1800035bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800035c3  jz      loc_1800036DA
0x1800035c9  cmp     rax, rbx
0x1800035cc  jb      loc_1800037A2
0x1800035d2  lea     rdi, [rax+1]
0x1800035d6  cmp     rdi, rax
0x1800035d9  jnb     short loc_180003645
0x1800035db  mov     r15d, 80070216h
0x1800035e1  test    r15d, r15d
0x1800035e4  jns     loc_1800037E0
0x1800035ea  test    r14, r14
0x1800035ed  jz      short loc_180003603
0x1800035ef  call    cs:__imp_GetProcessHeap
0x1800035f5  mov     r8, r14; lpMem
0x1800035f8  xor     edx, edx; dwFlags
0x1800035fa  mov     rcx, rax; hHeap
0x1800035fd  call    cs:__imp_HeapFree
0x180003603  mov     ebx, r15d
0x180003606  mov     r14, [rsp+88h+arg_0]
0x18000360e  test    ebx, ebx
0x180003610  js      loc_180003809
0x180003616  call    cs:__imp_GetProcessHeap
0x18000361c  mov     r8, rbp; lpMem
0x18000361f  xor     edx, edx; dwFlags
0x180003621  mov     rcx, rax; hHeap
0x180003624  call    cs:__imp_HeapFree
0x18000362a  xor     eax, eax
0x18000362c  lea     r11, [rsp+88h+var_28]
0x180003631  mov     rbx, [r11+38h]
0x180003635  mov     rbp, [r11+48h]
0x180003639  mov     rsp, r11
0x18000363c  pop     r15
0x18000363e  pop     r13
0x180003640  pop     r12
0x180003642  pop     rdi
0x180003643  pop     rsi
0x180003644  retn
0x180003645  mov     eax, 2
0x18000364a  mul     rdi
0x18000364d  mov     rsi, rax
0x180003650  test    rdx, rdx
0x180003653  jnz     short loc_1800035DB
0x180003655  call    cs:__imp_GetProcessHeap
0x18000365b  mov     r8, rsi; dwBytes
0x18000365e  xor     edx, edx; dwFlags
0x180003660  mov     rcx, rax; hHeap
0x180003663  call    cs:__imp_HeapAlloc
0x180003669  test    rax, rax
0x18000366c  jz      loc_1800035E1
0x180003672  mov     [rax], r13w
0x180003676  mov     r14, rax
0x180003679  mov     r15d, r13d
0x18000367c  test    rdi, rdi
0x18000367f  jz      loc_1800035E1
0x180003685  cmp     rdi, 7FFFFFFFh
0x18000368c  ja      loc_1800037D7
0x180003692  cmp     rbx, 7FFFFFFEh
0x180003699  ja      loc_1800037D7
0x18000369f  mov     rcx, rbp
0x1800036a2  mov     rdx, rax
0x1800036a5  test    rbx, rbx
0x1800036a8  jz      short loc_1800036D1
0x1800036aa  movzx   eax, word ptr [rcx]
0x1800036ad  test    ax, ax
0x1800036b0  jz      short loc_1800036CC
0x1800036b2  mov     [rdx], ax
0x1800036b5  add     rcx, 2
0x1800036b9  add     rdx, 2
0x1800036bd  dec     rbx
0x1800036c0  sub     rdi, 1
0x1800036c4  jnz     short loc_1800036A5
0x1800036c6  sub     rdx, 2
0x1800036ca  jmp     short loc_1800036D1
0x1800036cc  test    rdi, rdi
0x1800036cf  jz      short loc_1800036C6
0x1800036d1  mov     [rdx], r13w
0x1800036d5  jmp     loc_1800035E1
0x1800036da  mov     rax, rbx
0x1800036dd  jmp     loc_1800035D2
0x1800036e2  mov     edi, 39h ; '9'
0x1800036e7  mov     eax, 2
0x1800036ec  mul     rdi
0x1800036ef  mov     rsi, rax
0x1800036f2  test    rdx, rdx
0x1800036f5  jnz     short loc_180003763
0x1800036f7  call    cs:__imp_GetProcessHeap
0x1800036fd  mov     r8, rsi; dwBytes
0x180003700  xor     edx, edx; dwFlags
0x180003702  mov     rcx, rax; hHeap
0x180003705  call    cs:__imp_HeapAlloc
0x18000370b  mov     r8, rax
0x18000370e  test    rax, rax
0x180003711  jz      short loc_18000376D
0x180003713  mov     [rsp+88h+var_48], rdi
0x180003718  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x18000371f  mov     [rsp+88h+lpMem], rax
0x180003724  mov     ecx, 38h ; '8'
0x180003729  mov     [rax], r13w
0x18000372d  mov     esi, r13d
0x180003730  test    rcx, rcx
0x180003733  jz      loc_18000352A
0x180003739  movzx   eax, word ptr [rdx]
0x18000373c  test    ax, ax
0x18000373f  jz      loc_180003521
0x180003745  mov     [r8], ax
0x180003749  add     rdx, 2
0x18000374d  add     r8, 2
0x180003751  dec     rcx
0x180003754  sub     rdi, 1
0x180003758  jnz     short loc_180003730
0x18000375a  sub     r8, 2
0x18000375e  jmp     loc_18000352A
0x180003763  mov     esi, 80070216h
0x180003768  jmp     loc_180003537
0x18000376d  mov     esi, r15d
0x180003770  jmp     loc_180003537
0x180003775  mov     rcx, [rsp+88h]; this
0x18000377d  lea     r8, aOnecoreInterna_2; "OneCore\\internal\\DS\\inc\\profiles\\s"...
0x180003784  mov     r9d, esi; char *
0x180003787  mov     edx, 80h; void *
0x18000378c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003791  lea     rcx, [rsp+88h+lpMem]
0x180003796  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000379b  mov     eax, esi
0x18000379d  jmp     loc_18000362C
0x1800037a2  mov     rbx, rax
0x1800037a5  jmp     loc_1800035D2
0x1800037aa  mov     rcx, [rsp+88h]; this
0x1800037b2  lea     r8, aOnecoreInterna_2; "OneCore\\internal\\DS\\inc\\profiles\\s"...
0x1800037b9  mov     r9d, edi; char *
0x1800037bc  mov     edx, 81h; void *
0x1800037c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800037c6  lea     rcx, [rsp+88h+lpMem]
0x1800037cb  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800037d0  mov     eax, edi
0x1800037d2  jmp     loc_18000362C
0x1800037d7  mov     [rax], r13w
0x1800037db  jmp     loc_1800035E1
0x1800037e0  mov     ebx, r15d
0x1800037e3  jmp     short loc_1800037FA
0x1800037e5  lea     rcx, [rsp+88h+var_40]
0x1800037ea  mov     ebx, r13d
0x1800037ed  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800037f2  mov     r14, [rsp+88h+var_40]
0x1800037f7  mov     r15d, r13d
0x1800037fa  mov     [r12], r14
0x1800037fe  jmp     loc_180003606
0x180003803  mov     r15d, 80070490h
0x180003809  mov     rcx, [rsp+88h]; this
0x180003811  lea     r8, aOnecoreInterna_2; "OneCore\\internal\\DS\\inc\\profiles\\s"...
0x180003818  mov     r9d, r15d; char *
0x18000381b  mov     edx, 82h; void *
0x180003820  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003825  lea     rcx, [rsp+88h+lpMem]
0x18000382a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000382f  mov     eax, r15d
0x180003832  jmp     loc_18000362C
```
