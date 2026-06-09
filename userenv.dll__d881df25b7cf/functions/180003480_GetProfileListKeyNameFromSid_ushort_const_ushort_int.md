# GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)

- ea: `0x180003480`
- end: `0x1800038fe`
- name: `?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z`
- size: `1150`
- prototype: `__int64 __fastcall(LPCWCH lpString1, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180002490`

## callees

- `0x180003480`
- `0x180003910`
- `0x180003e90`
- `0x1800040b0`
- `0x18000db08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003693`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003693`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003716`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800037c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003716`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800037c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000367f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003702`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000367f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003702`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037b2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800034cc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800034fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000352a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003556`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003582`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800034cc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800034fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000352a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003556`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180003582`

## string_xrefs

- `0x180003844`: `OneCore\internal\DS\inc\profiles\sid.h`
- `0x180003879`: `OneCore\internal\DS\inc\profiles\sid.h`
- `0x1800038d8`: `OneCore\internal\DS\inc\profiles\sid.h`

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
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&lpMem);
      return (unsigned int)v6;
    }
  }
}

```

## disassembly

```asm
0x180003480  mov     [rsp+arg_8], rbx
0x180003485  mov     [rsp+arg_18], rbp
0x18000348a  push    rsi
0x18000348b  push    rdi
0x18000348c  push    r12
0x18000348e  push    r13
0x180003490  push    r15
0x180003492  sub     rsp, 60h
0x180003496  xor     r13d, r13d
0x180003499  mov     [rsp+88h+bIgnoreCase], 1; int
0x1800034a1  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800034a8  mov     [rdx], r13
0x1800034ab  mov     r12, rdx
0x1800034ae  mov     [rsp+88h+lpMem], r13
0x1800034b3  mov     edx, ebx; cchCount1
0x1800034b5  mov     [rsp+88h+var_50], r13
0x1800034ba  mov     r9d, ebx; cchCount2
0x1800034bd  mov     [rsp+88h+var_48], r13
0x1800034c2  lea     r8, String2; "S-1-5-18"
0x1800034c9  mov     rbp, rcx
0x1800034cc  call    cs:__imp_CompareStringOrdinal
0x1800034d3  nop     dword ptr [rax+rax+00h]
0x1800034d8  mov     r15d, 8007000Eh
0x1800034de  cmp     eax, 2
0x1800034e1  jz      loc_18000379D
0x1800034e7  mov     r9d, ebx; cchCount2
0x1800034ea  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x1800034f2  lea     r8, aS1519; "S-1-5-19"
0x1800034f9  mov     edx, ebx; cchCount1
0x1800034fb  mov     rcx, rbp; lpString1
0x1800034fe  call    cs:__imp_CompareStringOrdinal
0x180003505  nop     dword ptr [rax+rax+00h]
0x18000350a  cmp     eax, 2
0x18000350d  jz      loc_18000379D
0x180003513  mov     r9d, ebx; cchCount2
0x180003516  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x18000351e  lea     r8, aS1520; "S-1-5-20"
0x180003525  mov     edx, ebx; cchCount1
0x180003527  mov     rcx, rbp; lpString1
0x18000352a  call    cs:__imp_CompareStringOrdinal
0x180003531  nop     dword ptr [rax+rax+00h]
0x180003536  cmp     eax, 2
0x180003539  jz      loc_18000379D
0x18000353f  mov     r9d, ebx; cchCount2
0x180003542  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x18000354a  lea     r8, aS159321; "S-1-5-93-2-1"
0x180003551  mov     edx, ebx; cchCount1
0x180003553  mov     rcx, rbp; lpString1
0x180003556  call    cs:__imp_CompareStringOrdinal
0x18000355d  nop     dword ptr [rax+rax+00h]
0x180003562  cmp     eax, 2
0x180003565  jz      loc_18000379D
0x18000356b  mov     r9d, ebx; cchCount2
0x18000356e  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x180003576  lea     r8, aS159322; "S-1-5-93-2-2"
0x18000357d  mov     edx, ebx; cchCount1
0x18000357f  mov     rcx, rbp; lpString1
0x180003582  call    cs:__imp_CompareStringOrdinal
0x180003589  nop     dword ptr [rax+rax+00h]
0x18000358e  cmp     eax, 2
0x180003591  jz      loc_18000379D
0x180003597  lea     rcx, [rsp+88h+lpMem]; unsigned __int16 **
0x18000359c  mov     [rsp+88h+var_50], rbx
0x1800035a1  mov     [rsp+88h+var_48], rbx
0x1800035a6  call    ?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z; GetUserProfileListRootKeyName(ushort * *,int *)
0x1800035ab  mov     esi, eax
0x1800035ad  jmp     short loc_1800035C5
0x1800035af  test    rdi, rdi
0x1800035b2  jz      loc_180003821
0x1800035b8  mov     [r8], r13w
0x1800035bc  mov     [rsp+88h+var_50], 38h ; '8'
0x1800035c5  test    esi, esi
0x1800035c7  js      loc_18000383C
0x1800035cd  mov     r8, rbp
0x1800035d0  lea     rdx, aS_0; "\\%s"
0x1800035d7  lea     rcx, [rsp+88h+lpMem]
0x1800035dc  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1800035e1  mov     edi, eax
0x1800035e3  test    eax, eax
0x1800035e5  js      loc_180003871
0x1800035eb  mov     rbp, [rsp+88h+lpMem]
0x1800035f0  mov     [r12], r13
0x1800035f4  test    rbp, rbp
0x1800035f7  jz      loc_1800038CA
0x1800035fd  mov     rax, [rsp+88h+var_50]
0x180003602  mov     [rsp+88h+arg_0], r14
0x18000360a  mov     r14, r13
0x18000360d  mov     [rsp+88h+var_40], r13
0x180003612  mov     [rsp+88h+var_38], r13
0x180003617  mov     [rsp+88h+var_30], r13
0x18000361c  cmp     rax, rbx
0x18000361f  jnz     short loc_18000362F
0x180003621  mov     rax, rbx
0x180003624  inc     rax
0x180003627  cmp     [rbp+rax*2+0], r13w
0x18000362d  jnz     short loc_180003624
0x18000362f  test    rbp, rbp
0x180003632  jz      loc_1800038AC
0x180003638  nop     dword ptr [rax+rax+00000000h]
0x180003640  inc     rbx
0x180003643  cmp     [rbp+rbx*2+0], r13w
0x180003649  jnz     short loc_180003640
0x18000364b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000364f  jz      loc_180003795
0x180003655  cmp     rax, rbx
0x180003658  jb      loc_180003869
0x18000365e  lea     rdi, [rax+1]
0x180003662  cmp     rdi, rax
0x180003665  jnb     loc_1800036EE
0x18000366b  mov     r15d, 80070216h
0x180003671  test    r15d, r15d
0x180003674  jns     loc_1800038A7
0x18000367a  test    r14, r14
0x18000367d  jz      short loc_18000369F
0x18000367f  call    cs:__imp_GetProcessHeap
0x180003686  nop     dword ptr [rax+rax+00h]
0x18000368b  mov     r8, r14; lpMem
0x18000368e  xor     edx, edx; dwFlags
0x180003690  mov     rcx, rax; hHeap
0x180003693  call    cs:__imp_HeapFree
0x18000369a  nop     dword ptr [rax+rax+00h]
0x18000369f  mov     ebx, r15d
0x1800036a2  mov     r14, [rsp+88h+arg_0]
0x1800036aa  test    ebx, ebx
0x1800036ac  js      loc_1800038D0
0x1800036b2  call    cs:__imp_GetProcessHeap
0x1800036b9  nop     dword ptr [rax+rax+00h]
0x1800036be  mov     r8, rbp; lpMem
0x1800036c1  xor     edx, edx; dwFlags
0x1800036c3  mov     rcx, rax; hHeap
0x1800036c6  call    cs:__imp_HeapFree
0x1800036cd  nop     dword ptr [rax+rax+00h]
0x1800036d2  xor     eax, eax
0x1800036d4  lea     r11, [rsp+88h+var_28]
0x1800036d9  mov     rbx, [r11+38h]
0x1800036dd  mov     rbp, [r11+48h]
0x1800036e1  mov     rsp, r11
0x1800036e4  pop     r15
0x1800036e6  pop     r13
0x1800036e8  pop     r12
0x1800036ea  pop     rdi
0x1800036eb  pop     rsi
0x1800036ec  retn
0x1800036ee  mov     eax, 2
0x1800036f3  mul     rdi
0x1800036f6  mov     rsi, rax
0x1800036f9  test    rdx, rdx
0x1800036fc  jnz     loc_18000366B
0x180003702  call    cs:__imp_GetProcessHeap
0x180003709  nop     dword ptr [rax+rax+00h]
0x18000370e  mov     r8, rsi; dwBytes
0x180003711  xor     edx, edx; dwFlags
0x180003713  mov     rcx, rax; hHeap
0x180003716  call    cs:__imp_HeapAlloc
0x18000371d  nop     dword ptr [rax+rax+00h]
0x180003722  test    rax, rax
0x180003725  jz      loc_180003671
0x18000372b  mov     [rax], r13w
0x18000372f  mov     r14, rax
0x180003732  mov     r15d, r13d
0x180003735  test    rdi, rdi
0x180003738  jz      loc_180003671
0x18000373e  cmp     rdi, 7FFFFFFFh
0x180003745  ja      loc_18000389E
0x18000374b  cmp     rbx, 7FFFFFFEh
0x180003752  ja      loc_18000389E
0x180003758  mov     rcx, rbp
0x18000375b  mov     rdx, rax
0x18000375e  xchg    ax, ax
0x180003760  test    rbx, rbx
0x180003763  jz      short loc_18000378C
0x180003765  movzx   eax, word ptr [rcx]
0x180003768  test    ax, ax
0x18000376b  jz      short loc_180003787
0x18000376d  mov     [rdx], ax
0x180003770  add     rcx, 2
0x180003774  add     rdx, 2
0x180003778  dec     rbx
0x18000377b  sub     rdi, 1
0x18000377f  jnz     short loc_180003760
0x180003781  sub     rdx, 2
0x180003785  jmp     short loc_18000378C
0x180003787  test    rdi, rdi
0x18000378a  jz      short loc_180003781
0x18000378c  mov     [rdx], r13w
0x180003790  jmp     loc_180003671
0x180003795  mov     rax, rbx
0x180003798  jmp     loc_18000365E
0x18000379d  mov     edi, 39h ; '9'
0x1800037a2  mov     eax, 2
0x1800037a7  mul     rdi
0x1800037aa  mov     rsi, rax
0x1800037ad  test    rdx, rdx
0x1800037b0  jnz     short loc_18000382A
0x1800037b2  call    cs:__imp_GetProcessHeap
0x1800037b9  nop     dword ptr [rax+rax+00h]
0x1800037be  mov     r8, rsi; dwBytes
0x1800037c1  xor     edx, edx; dwFlags
0x1800037c3  mov     rcx, rax; hHeap
0x1800037c6  call    cs:__imp_HeapAlloc
0x1800037cd  nop     dword ptr [rax+rax+00h]
0x1800037d2  mov     r8, rax
0x1800037d5  test    rax, rax
0x1800037d8  jz      short loc_180003834
0x1800037da  mov     [rsp+88h+var_48], rdi
0x1800037df  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800037e6  mov     [rsp+88h+lpMem], rax
0x1800037eb  mov     ecx, 38h ; '8'
0x1800037f0  mov     [rax], r13w
0x1800037f4  mov     esi, r13d
0x1800037f7  test    rcx, rcx
0x1800037fa  jz      loc_1800035B8
0x180003800  movzx   eax, word ptr [rdx]
0x180003803  test    ax, ax
0x180003806  jz      loc_1800035AF
0x18000380c  mov     [r8], ax
0x180003810  add     rdx, 2
0x180003814  add     r8, 2
0x180003818  dec     rcx
0x18000381b  sub     rdi, 1
0x18000381f  jnz     short loc_1800037F7
0x180003821  sub     r8, 2
0x180003825  jmp     loc_1800035B8
0x18000382a  mov     esi, 80070216h
0x18000382f  jmp     loc_1800035C5
0x180003834  mov     esi, r15d
0x180003837  jmp     loc_1800035C5
0x18000383c  mov     rcx, [rsp+88h]; this
0x180003844  lea     r8, aOnecoreInterna_2; "OneCore\\internal\\DS\\inc\\profiles\\s"...
0x18000384b  mov     r9d, esi; char *
0x18000384e  mov     edx, 80h; void *
0x180003853  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003858  lea     rcx, [rsp+88h+lpMem]
0x18000385d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180003862  mov     eax, esi
0x180003864  jmp     loc_1800036D4
0x180003869  mov     rbx, rax
0x18000386c  jmp     loc_18000365E
0x180003871  mov     rcx, [rsp+88h]; this
0x180003879  lea     r8, aOnecoreInterna_2; "OneCore\\internal\\DS\\inc\\profiles\\s"...
0x180003880  mov     r9d, edi; char *
0x180003883  mov     edx, 81h; void *
0x180003888  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000388d  lea     rcx, [rsp+88h+lpMem]
0x180003892  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180003897  mov     eax, edi
0x180003899  jmp     loc_1800036D4
0x18000389e  mov     [rax], r13w
0x1800038a2  jmp     loc_180003671
0x1800038a7  mov     ebx, r15d
0x1800038aa  jmp     short loc_1800038C1
0x1800038ac  lea     rcx, [rsp+88h+var_40]
0x1800038b1  mov     ebx, r13d
0x1800038b4  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800038b9  mov     r14, [rsp+88h+var_40]
0x1800038be  mov     r15d, r13d
0x1800038c1  mov     [r12], r14
0x1800038c5  jmp     loc_1800036A2
0x1800038ca  mov     r15d, 80070490h
0x1800038d0  mov     rcx, [rsp+88h]; this
0x1800038d8  lea     r8, aOnecoreInterna_2; "OneCore\\internal\\DS\\inc\\profiles\\s"...
0x1800038df  mov     r9d, r15d; char *
0x1800038e2  mov     edx, 82h; void *
0x1800038e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800038ec  lea     rcx, [rsp+88h+lpMem]
0x1800038f1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800038f6  mov     eax, r15d
0x1800038f9  jmp     loc_1800036D4
```
