# LNegotiateAPIVersion

- ea: `0x180011820`
- end: `0x180011b0a`
- name: `LNegotiateAPIVersion`
- size: `746`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned int, _OWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180028100`

## callees

- `0x180006f24`
- `0x180011820`
- `0x18001f514`
- `0x18003dc84`
- `0x180040010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800119d6`
- `KERNEL32!LeaveCriticalSection` at `0x1800119d6`

## string_xrefs

- `0x180011ac9`: `LNegotiateAPIVersion: LINEERR_INCOMPATIBLEAPIVERSION1`
- `0x180011a29`: `LNegotiateAPIVersion: LINEERR_INCOMPATIBLEAPIVERSION2`
- `0x180011987`: `LNegotiateAPIVersion WaitForExclusiveLineAppAccess succeeded returned ptLineApp %p for hLineApp %Iu`
- `0x180011ab0`: `LNegotiateAPIVersion WaitForExclusiveLineAppAccess returned NULL`
- `0x180011aa7`: `LNegotiateAPIVersion: LINEERR_INCOMPATIBLEAPIVERSION3`

## pseudocode

```c
__int64 __fastcall LNegotiateAPIVersion(__int64 a1, _DWORD *a2, unsigned int a3, _OWORD *a4, _DWORD *a5)
{
  __int64 v9; // r15
  __int64 result; // rax
  unsigned int v11; // eax
  unsigned int v12; // esi
  unsigned int v13; // ebx
  const void *v14; // rax
  unsigned __int64 v15; // r14
  char *LineLookupEntry; // rax
  char *v17; // r8
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 (__fastcall *v20)(_QWORD, __int64, _OWORD *); // rax
  int v21; // eax

  v9 = (unsigned int)a2[3];
  result = TRACELogPrint(
             524290,
             "LNegotiateAPIVersion: started. dwDeviceID %lx, dwAPILowVersion %lx dwAPIHighVersion %lx",
             a2[3],
             a2[4],
             a2[5]);
  if ( a3 < 0x10 )
  {
    *a2 = -2147483576;
    return result;
  }
  if ( dword_180051918 )
  {
    if ( (dword_180051900 & 2) != 0 && (*(_BYTE *)(a1 + 216) & 1) == 0 )
    {
      if ( (unsigned int)v9 >= *(_DWORD *)(a1 + 96) )
      {
        *a2 = -2147483646;
        return TRACELogPrint(524290, "lineNegotiateAPIVersion: exit, result=x%x", *a2);
      }
      _mm_lfence();
      LODWORD(v9) = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 4 * v9);
    }
    if ( (unsigned int)v9 >= dword_18005191C )
    {
      *a2 = -2147483646;
      return TRACELogPrint(524290, "lineNegotiateAPIVersion: exit, result=x%x", *a2);
    }
    v11 = a2[5];
    v12 = a2[4];
    if ( v12 > v11 || (v13 = 196609, v12 > 0x30001) || v11 < 0x10003 )
    {
      TRACELogPrint(65538, "LNegotiateAPIVersion: LINEERR_INCOMPATIBLEAPIVERSION1");
      goto LABEL_54;
    }
    if ( (v11 & 0xC0000000) != 0 )
    {
      v11 = 65539;
      if ( v12 > 0x10003 )
        v11 = a2[4];
    }
    if ( v11 < 0x30001 )
    {
      v13 = 196608;
      if ( v11 < 0x30000 || v12 > 0x30000 )
      {
        v13 = 131074;
        if ( v11 < 0x20002 || v12 > 0x20002 )
        {
          v13 = 131073;
          if ( v11 < 0x20001 || v12 > 0x20001 )
          {
            if ( v11 < 0x20000 || v12 > 0x20000 )
            {
              if ( v11 < 0x10004 || v12 > 0x10004 )
              {
                if ( v12 > 0x10003 )
                {
                  TRACELogPrint(65538, "LNegotiateAPIVersion: LINEERR_INCOMPATIBLEAPIVERSION2");
                  goto LABEL_54;
                }
                v13 = 65539;
              }
              else
              {
                v13 = 65540;
              }
            }
            else
            {
              v13 = 0x20000;
            }
          }
        }
      }
    }
    v14 = (const void *)WaitForExclusiveLineAppAccess((unsigned int)a2[2], a1);
    v15 = (unsigned __int64)v14;
    if ( v14 )
    {
      TRACELogPrint(
        262146,
        "LNegotiateAPIVersion WaitForExclusiveLineAppAccess succeeded returned ptLineApp %p for hLineApp %Iu",
        v14,
        a2[2]);
      if ( *(_DWORD *)(v15 + 48) < 0x20000u )
        v13 = 65540 - (v13 < 0x10004);
      if ( v13 > *(_DWORD *)(v15 + 48) )
        *(_DWORD *)(v15 + 48) = v13;
      LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (v15 >> 4)));
      LineLookupEntry = GetLineLookupEntry(v9);
      v17 = LineLookupEntry;
      if ( LineLookupEntry )
      {
        if ( *((_DWORD *)LineLookupEntry + 8) )
        {
          *a2 = -2147483582;
          return TRACELogPrint(524290, "lineNegotiateAPIVersion: exit, result=x%x", *a2);
        }
        if ( !*((_QWORD *)LineLookupEntry + 3) )
        {
          *a2 = -2147483581;
          return TRACELogPrint(524290, "lineNegotiateAPIVersion: exit, result=x%x", *a2);
        }
        v18 = *(unsigned int *)LineLookupEntry;
        if ( v12 <= (unsigned int)v18 )
        {
          v19 = *(_DWORD *)LineLookupEntry;
          if ( v13 <= (unsigned int)v18 )
            v19 = v13;
          a2[6] = v19;
          v20 = *(__int64 (__fastcall **)(_QWORD, __int64, _OWORD *))(*((_QWORD *)v17 + 3) + 368LL);
          if ( !v20 || (v21 = v20((unsigned int)v9, v18, a4), *a2 = v21, v21 == -2147483575) )
          {
            *a2 = 0;
            *a4 = 0;
          }
          a2[7] = 0;
          a2[8] = 16;
          *a5 = 76;
          return TRACELogPrint(524290, "lineNegotiateAPIVersion: exit, result=x%x", *a2);
        }
        TRACELogPrint(65538, "LNegotiateAPIVersion: LINEERR_INCOMPATIBLEAPIVERSION3");
LABEL_54:
        *a2 = -2147483636;
        return TRACELogPrint(524290, "lineNegotiateAPIVersion: exit, result=x%x", *a2);
      }
    }
    else
    {
      TRACELogPrint(65538, "LNegotiateAPIVersion WaitForExclusiveLineAppAccess returned NULL");
    }
    *a2 = -2147483628;
    return TRACELogPrint(524290, "lineNegotiateAPIVersion: exit, result=x%x", *a2);
  }
  *a2 = -2147483568;
  return TRACELogPrint(524290, "lineNegotiateAPIVersion: exit, result=x%x", *a2);
}

```

## disassembly

```asm
0x180011820  mov     [rsp+arg_8], rdx
0x180011825  push    rbx
0x180011826  push    rsi
0x180011827  push    rdi
0x180011828  push    r12
0x18001182a  push    r14
0x18001182c  push    r15
0x18001182e  sub     rsp, 48h
0x180011832  mov     r12, r9
0x180011835  mov     ebx, r8d
0x180011838  mov     rdi, rdx
0x18001183b  mov     r14, rcx
0x18001183e  mov     r15d, [rdx+0Ch]
0x180011842  mov     eax, [rdx+14h]
0x180011845  mov     [rsp+78h+var_58], eax
0x180011849  mov     r9d, [rdx+10h]
0x18001184d  mov     r8d, r15d
0x180011850  lea     rdx, aLnegotiateapiv_1; "LNegotiateAPIVersion: started. dwDevice"...
0x180011857  mov     ecx, 80002h
0x18001185c  call    TRACELogPrint
0x180011861  cmp     ebx, 10h
0x180011864  jnb     short loc_180011871
0x180011866  mov     dword ptr [rdi], 80000048h
0x18001186c  jmp     loc_180011AFC
0x180011871  cmp     cs:dword_180051918, 0
0x180011878  jnz     short loc_180011885
0x18001187a  mov     dword ptr [rdi], 80000050h
0x180011880  jmp     loc_180011AE8
0x180011885  test    byte ptr cs:dword_180051900, 2
0x18001188c  jz      short loc_1800118DF
0x18001188e  test    byte ptr [r14+0D8h], 1
0x180011896  jnz     short loc_1800118DF
0x180011898  cmp     r15d, [r14+60h]
0x18001189c  jb      short loc_1800118A9
0x18001189e  mov     dword ptr [rdi], 80000002h
0x1800118a4  jmp     loc_180011AE8
0x1800118a9  lfence
0x1800118ac  mov     rax, [r14+58h]
0x1800118b0  mov     r15d, [rax+r15*4]
0x1800118b4  mov     [rsp+78h+var_48], r15d
0x1800118b9  jmp     short loc_1800118DF
0x1800118bb  lea     rdx, aPtclientExcept; "ptClient excepted in LineNegotiateAPIVe"...
0x1800118c2  mov     ecx, 10002h
0x1800118c7  call    TRACELogPrint
0x1800118cc  mov     rdi, [rsp+78h+arg_8]
0x1800118d4  mov     dword ptr [rdi], 8000002Bh
0x1800118da  jmp     loc_180011AE8
0x1800118df  cmp     r15d, cs:dword_18005191C
0x1800118e6  jnb     loc_180011AE2
0x1800118ec  mov     eax, [rdi+14h]
0x1800118ef  mov     esi, [rdi+10h]
0x1800118f2  cmp     esi, eax
0x1800118f4  ja      loc_180011AC9
0x1800118fa  mov     ebx, 30001h
0x1800118ff  cmp     esi, ebx
0x180011901  ja      loc_180011AC9
0x180011907  mov     ecx, 10003h
0x18001190c  cmp     eax, ecx
0x18001190e  jb      loc_180011AC9
0x180011914  test    eax, 0C0000000h
0x180011919  jz      short loc_180011922
0x18001191b  mov     eax, ecx
0x18001191d  cmp     esi, ecx
0x18001191f  cmova   eax, esi
0x180011922  cmp     eax, ebx
0x180011924  jnb     short loc_180011969
0x180011926  mov     ebx, 30000h
0x18001192b  cmp     eax, ebx
0x18001192d  jb      short loc_180011933
0x18001192f  cmp     esi, ebx
0x180011931  jbe     short loc_180011969
0x180011933  mov     ebx, 20002h
0x180011938  cmp     eax, ebx
0x18001193a  jb      short loc_180011940
0x18001193c  cmp     esi, ebx
0x18001193e  jbe     short loc_180011969
0x180011940  mov     ebx, 20001h
0x180011945  cmp     eax, ebx
0x180011947  jb      short loc_18001194D
0x180011949  cmp     esi, ebx
0x18001194b  jbe     short loc_180011969
0x18001194d  cmp     eax, 20000h
0x180011952  jb      loc_180011A01
0x180011958  cmp     esi, 20000h
0x18001195e  ja      loc_180011A01
0x180011964  mov     ebx, 20000h
0x180011969  mov     rdx, r14
0x18001196c  mov     ecx, [rdi+8]
0x18001196f  call    WaitForExclusiveLineAppAccess
0x180011974  mov     r14, rax
0x180011977  test    rax, rax
0x18001197a  jz      loc_180011AB0
0x180011980  mov     r9d, [rdi+8]
0x180011984  mov     r8, rax
0x180011987  lea     rdx, aLnegotiateapiv_4; "LNegotiateAPIVersion WaitForExclusiveLi"...
0x18001198e  mov     ecx, 40002h
0x180011993  call    TRACELogPrint
0x180011998  cmp     dword ptr [r14+30h], 20000h
0x1800119a0  jnb     short loc_1800119B0
0x1800119a2  cmp     ebx, 10004h
0x1800119a8  sbb     ebx, ebx
0x1800119aa  add     ebx, 10004h
0x1800119b0  cmp     ebx, [r14+30h]
0x1800119b4  jbe     short loc_1800119BA
0x1800119b6  mov     [r14+30h], ebx
0x1800119ba  shr     r14, 4
0x1800119be  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800119c4  and     r14, rax
0x1800119c7  lea     rcx, [r14+r14*4]
0x1800119cb  mov     rax, cs:gLockTable
0x1800119d2  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800119d6  call    cs:__imp_LeaveCriticalSection
0x1800119dc  mov     ecx, r15d
0x1800119df  call    GetLineLookupEntry
0x1800119e4  mov     r8, rax
0x1800119e7  test    rax, rax
0x1800119ea  jz      loc_180011AC1
0x1800119f0  cmp     dword ptr [rax+20h], 0
0x1800119f4  jz      short loc_180011A35
0x1800119f6  mov     dword ptr [rdi], 80000042h
0x1800119fc  jmp     loc_180011AE8
0x180011a01  cmp     eax, 10004h
0x180011a06  jb      short loc_180011A1A
0x180011a08  cmp     esi, 10004h
0x180011a0e  ja      short loc_180011A1A
0x180011a10  mov     ebx, 10004h
0x180011a15  jmp     loc_180011969
0x180011a1a  cmp     eax, ecx
0x180011a1c  jb      short loc_180011A29
0x180011a1e  cmp     esi, ecx
0x180011a20  ja      short loc_180011A29
0x180011a22  mov     ebx, ecx
0x180011a24  jmp     loc_180011969
0x180011a29  lea     rdx, aLnegotiateapiv_2; "LNegotiateAPIVersion: LINEERR_INCOMPATI"...
0x180011a30  jmp     loc_180011AD0
0x180011a35  cmp     qword ptr [rax+18h], 0
0x180011a3a  jnz     short loc_180011A47
0x180011a3c  mov     dword ptr [rdi], 80000043h
0x180011a42  jmp     loc_180011AE8
0x180011a47  mov     edx, [rax]
0x180011a49  cmp     esi, edx
0x180011a4b  ja      short loc_180011AA7
0x180011a4d  mov     eax, edx
0x180011a4f  cmp     ebx, edx
0x180011a51  cmovbe  eax, ebx
0x180011a54  mov     [rdi+18h], eax
0x180011a57  mov     rax, [r8+18h]
0x180011a5b  mov     rax, [rax+170h]
0x180011a62  test    rax, rax
0x180011a65  jz      short loc_180011A7B
0x180011a67  mov     r8, r12
0x180011a6a  mov     ecx, r15d
0x180011a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a72  mov     [rdi], eax
0x180011a74  cmp     eax, 80000049h
0x180011a79  jnz     short loc_180011A89
0x180011a7b  mov     dword ptr [rdi], 0
0x180011a81  xorps   xmm0, xmm0
0x180011a84  movups  xmmword ptr [r12], xmm0
0x180011a89  mov     dword ptr [rdi+1Ch], 0
0x180011a90  mov     dword ptr [rdi+20h], 10h
0x180011a97  mov     rax, [rsp+78h+arg_20]
0x180011a9f  mov     dword ptr [rax], 4Ch ; 'L'
0x180011aa5  jmp     short loc_180011AE8
0x180011aa7  lea     rdx, aLnegotiateapiv; "LNegotiateAPIVersion: LINEERR_INCOMPATI"...
0x180011aae  jmp     short loc_180011AD0
0x180011ab0  lea     rdx, aLnegotiateapiv_3; "LNegotiateAPIVersion WaitForExclusiveLi"...
0x180011ab7  mov     ecx, 10002h
0x180011abc  call    TRACELogPrint
0x180011ac1  mov     dword ptr [rdi], 80000014h
0x180011ac7  jmp     short loc_180011AE8
0x180011ac9  lea     rdx, aLnegotiateapiv_0; "LNegotiateAPIVersion: LINEERR_INCOMPATI"...
0x180011ad0  mov     ecx, 10002h
0x180011ad5  call    TRACELogPrint
0x180011ada  mov     dword ptr [rdi], 8000000Ch
0x180011ae0  jmp     short loc_180011AE8
0x180011ae2  mov     dword ptr [rdi], 80000002h
0x180011ae8  mov     r8d, [rdi]
0x180011aeb  lea     rdx, aLinenegotiatea; "lineNegotiateAPIVersion: exit, result=x"...
0x180011af2  mov     ecx, 80002h
0x180011af7  call    TRACELogPrint
0x180011afc  add     rsp, 48h
0x180011b00  pop     r15
0x180011b02  pop     r14
0x180011b04  pop     r12
0x180011b06  pop     rdi
0x180011b07  pop     rsi
0x180011b08  pop     rbx
0x180011b09  retn
```
