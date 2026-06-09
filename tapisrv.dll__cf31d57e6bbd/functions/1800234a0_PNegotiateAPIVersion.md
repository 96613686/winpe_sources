# PNegotiateAPIVersion

- ea: `0x1800234a0`
- end: `0x1800237f4`
- name: `PNegotiateAPIVersion`
- size: `852`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028100`

## callees

- `0x180021640`
- `0x1800234a0`
- `0x180026004`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e3b4`
- `0x180040010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180023650`
- `KERNEL32!LeaveCriticalSection` at `0x180023650`

## string_xrefs

- `0x1800236b9`: `   Incompatible version`
- `0x18002379b`: `  phone removed...`
- `0x180023733`: `  ExtensionID0=x%08lx`
- `0x18002374a`: `  ExtensionID1=x%08lx`
- `0x18002375c`: `  ExtensionID2=x%08lx`
- `0x18002376e`: `  ExtensionID3=x%08lx`

## pseudocode

```c
_UNKNOWN **__fastcall PNegotiateAPIVersion(__int64 a1, _DWORD *a2, unsigned int a3, _DWORD *a4, _DWORD *a5)
{
  _UNKNOWN **result; // rax
  __int64 v8; // r15
  unsigned int v9; // esi
  unsigned int v10; // r14d
  __int64 v11; // rcx
  unsigned __int64 v12; // r12
  unsigned int v13; // edi
  char *PhoneLookupEntry; // rax
  char *v15; // r8
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 (__fastcall *v18)(_QWORD, __int64, _DWORD *); // rax
  int v19; // eax
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a3 < 0x10 )
  {
    *a2 = -1879048164;
    return result;
  }
  if ( dword_180051928 )
  {
    v8 = (unsigned int)a2[3];
    if ( (dword_180051900 & 2) != 0 && (*(_BYTE *)(a1 + 216) & 1) == 0 )
    {
      if ( (unsigned int)v8 >= *(_DWORD *)(a1 + 120) )
      {
        *a2 = -1879048190;
        return (_UNKNOWN **)TRACELogPrint(524290, "phoneNegotiateAPIVersion: exit, result=x%x", *a2);
      }
      _mm_lfence();
      LODWORD(v8) = *(_DWORD *)(*(_QWORD *)(a1 + 112) + 4 * v8);
    }
    if ( (unsigned int)v8 >= dword_18005192C )
    {
      *a2 = -1879048190;
      return (_UNKNOWN **)TRACELogPrint(524290, "phoneNegotiateAPIVersion: exit, result=x%x", *a2);
    }
    v9 = a2[5];
    v10 = a2[4];
    v12 = ReferenceObject(a1, (unsigned int)a2[2], 1347436880);
    if ( !v12 )
    {
      *a2 = dword_180051928 != 0 ? -1879048185 : -1879048158;
      return (_UNKNOWN **)TRACELogPrint(524290, "phoneNegotiateAPIVersion: exit, result=x%x", *a2);
    }
    if ( v10 > v9 )
      goto LABEL_41;
    v13 = 196609;
    if ( v10 > 0x30001 || v9 < 0x10003 )
      goto LABEL_41;
    if ( v9 < 0x30001 )
    {
      v13 = 196608;
      if ( v9 < 0x30000 || v10 > 0x30000 )
      {
        v13 = 131074;
        if ( v9 < 0x20002 || v10 > 0x20002 )
        {
          v13 = 131073;
          if ( v9 < 0x20001 || v10 > 0x20001 )
          {
            if ( v9 < 0x20000 || v10 > 0x20000 )
            {
              if ( v9 < 0x10004 || v10 > 0x10004 )
              {
                if ( v10 > 0x10003 )
                {
                  TRACELogPrint(65538, "   Incompatible version");
                  goto LABEL_41;
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
    if ( !WaitForExclusivePhoneAppAccess((unsigned int)a2[2], a1) )
    {
      *a2 = -1879048185;
      goto LABEL_42;
    }
    if ( *(_DWORD *)(v12 + 64) < 0x20000u )
      v13 = 65540 - (v13 < 0x10004);
    if ( v13 > *(_DWORD *)(v12 + 64) )
      *(_DWORD *)(v12 + 64) = v13;
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (v12 >> 4)));
    PhoneLookupEntry = GetPhoneLookupEntry(v8);
    v15 = PhoneLookupEntry;
    if ( !PhoneLookupEntry || *((_DWORD *)PhoneLookupEntry + 8) )
    {
      TRACELogPrint(65538, "  phone removed...", PhoneLookupEntry);
      *a2 = -1879048168;
      goto LABEL_42;
    }
    if ( !*((_QWORD *)PhoneLookupEntry + 3) )
    {
      TRACELogPrint(65538, "  Provider == NULL", PhoneLookupEntry);
      *a2 = -1879048167;
LABEL_42:
      DereferenceObject(v11, a2[2], 1);
      return (_UNKNOWN **)TRACELogPrint(524290, "phoneNegotiateAPIVersion: exit, result=x%x", *a2);
    }
    v16 = *(unsigned int *)PhoneLookupEntry;
    if ( v10 <= (unsigned int)v16 )
    {
      v17 = *(_DWORD *)PhoneLookupEntry;
      if ( v13 <= (unsigned int)v16 )
        v17 = v13;
      a2[6] = v17;
      v18 = *(__int64 (__fastcall **)(_QWORD, __int64, _DWORD *))(*((_QWORD *)v15 + 3) + 768LL);
      if ( v18 )
      {
        v19 = v18((unsigned int)v8, v16, a4);
        *a2 = v19;
        if ( v19 )
          goto LABEL_42;
      }
      else
      {
        *(_OWORD *)a4 = 0;
      }
      a2[7] = 0;
      a2[8] = 16;
      TRACELogPrint(262146, "  ExtensionID0=x%08lx", *a4);
      TRACELogPrint(262146, "  ExtensionID1=x%08lx", a4[1]);
      TRACELogPrint(262146, "  ExtensionID2=x%08lx", a4[2]);
      TRACELogPrint(262146, "  ExtensionID3=x%08lx", a4[3]);
      *a5 = 76;
      goto LABEL_42;
    }
    TRACELogPrint(65538, "  API version too high");
LABEL_41:
    *a2 = -1879048189;
    goto LABEL_42;
  }
  *a2 = -1879048158;
  return (_UNKNOWN **)TRACELogPrint(524290, "phoneNegotiateAPIVersion: exit, result=x%x", *a2);
}

```

## disassembly

```asm
0x1800234a0  mov     rax, rsp
0x1800234a3  mov     [rax+8], rbx
0x1800234a7  mov     [rax+18h], rsi
0x1800234ab  mov     [rax+20h], r9
0x1800234af  mov     [rax+10h], rdx
0x1800234b3  push    rdi
0x1800234b4  push    r12
0x1800234b6  push    r13
0x1800234b8  push    r14
0x1800234ba  push    r15
0x1800234bc  sub     rsp, 30h
0x1800234c0  mov     rbx, rdx
0x1800234c3  mov     r13, rcx
0x1800234c6  cmp     r8d, 10h
0x1800234ca  jnb     short loc_1800234D7
0x1800234cc  mov     dword ptr [rdx], 9000001Ch
0x1800234d2  jmp     loc_1800237DC
0x1800234d7  cmp     cs:dword_180051928, 0
0x1800234de  jnz     short loc_1800234EB
0x1800234e0  mov     dword ptr [rdx], 90000022h
0x1800234e6  jmp     loc_1800237C8
0x1800234eb  mov     r15d, [rdx+0Ch]
0x1800234ef  test    byte ptr cs:dword_180051900, 2
0x1800234f6  jz      short loc_180023545
0x1800234f8  test    byte ptr [rcx+0D8h], 1
0x1800234ff  jnz     short loc_180023545
0x180023501  cmp     r15d, [rcx+78h]
0x180023505  jb      short loc_180023512
0x180023507  mov     dword ptr [rdx], 90000002h
0x18002350d  jmp     loc_1800237C8
0x180023512  lfence
0x180023515  mov     rax, [rcx+70h]
0x180023519  mov     r15d, [rax+r15*4]
0x18002351d  mov     [rsp+58h+var_38], r15d
0x180023522  jmp     short loc_180023545
0x180023524  lea     rdx, aPtclientExcept_0; "ptClient excepted in PhoneNegotiateAPIV"...
0x18002352b  mov     ecx, 10002h
0x180023530  call    TRACELogPrint
0x180023535  mov     rbx, [rsp+58h+arg_8]
0x18002353a  mov     dword ptr [rbx], 90000013h
0x180023540  jmp     loc_1800237C8
0x180023545  cmp     r15d, cs:dword_18005192C
0x18002354c  jnb     loc_1800237C2
0x180023552  mov     esi, [rdx+14h]
0x180023555  mov     r14d, [rdx+10h]
0x180023559  mov     r8d, 50504150h
0x18002355f  mov     edx, [rdx+8]
0x180023562  call    ReferenceObject
0x180023567  mov     r12, rax
0x18002356a  test    rax, rax
0x18002356d  jnz     short loc_180023589
0x18002356f  mov     eax, cs:dword_180051928
0x180023575  neg     eax
0x180023577  sbb     ecx, ecx
0x180023579  and     ecx, 0FFFFFFE5h
0x18002357c  add     ecx, 90000022h
0x180023582  mov     [rbx], ecx
0x180023584  jmp     loc_1800237C8
0x180023589  cmp     r14d, esi
0x18002358c  ja      loc_1800236CA
0x180023592  mov     edi, 30001h
0x180023597  cmp     r14d, edi
0x18002359a  ja      loc_1800236CA
0x1800235a0  mov     eax, 10003h
0x1800235a5  cmp     esi, eax
0x1800235a7  jb      loc_1800236CA
0x1800235ad  cmp     esi, edi
0x1800235af  jnb     short loc_1800235F9
0x1800235b1  mov     edi, 30000h
0x1800235b6  cmp     esi, edi
0x1800235b8  jb      short loc_1800235BF
0x1800235ba  cmp     r14d, edi
0x1800235bd  jbe     short loc_1800235F9
0x1800235bf  mov     edi, 20002h
0x1800235c4  cmp     esi, edi
0x1800235c6  jb      short loc_1800235CD
0x1800235c8  cmp     r14d, edi
0x1800235cb  jbe     short loc_1800235F9
0x1800235cd  mov     edi, 20001h
0x1800235d2  cmp     esi, edi
0x1800235d4  jb      short loc_1800235DB
0x1800235d6  cmp     r14d, edi
0x1800235d9  jbe     short loc_1800235F9
0x1800235db  cmp     esi, 20000h
0x1800235e1  jb      loc_180023692
0x1800235e7  cmp     r14d, 20000h
0x1800235ee  ja      loc_180023692
0x1800235f4  mov     edi, 20000h
0x1800235f9  mov     rdx, r13
0x1800235fc  mov     ecx, [rbx+8]
0x1800235ff  call    WaitForExclusivePhoneAppAccess
0x180023604  xor     esi, esi
0x180023606  test    rax, rax
0x180023609  jz      loc_1800237B7
0x18002360f  cmp     dword ptr [r12+40h], 20000h
0x180023618  jnb     short loc_180023628
0x18002361a  cmp     edi, 10004h
0x180023620  sbb     edi, edi
0x180023622  add     edi, 10004h
0x180023628  cmp     edi, [r12+40h]
0x18002362d  jbe     short loc_180023634
0x18002362f  mov     [r12+40h], edi
0x180023634  shr     r12, 4
0x180023638  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18002363e  and     r12, rax
0x180023641  lea     rcx, [r12+r12*4]
0x180023645  mov     rax, cs:gLockTable
0x18002364c  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180023650  call    cs:__imp_LeaveCriticalSection
0x180023656  mov     ecx, r15d
0x180023659  call    GetPhoneLookupEntry
0x18002365e  mov     r8, rax
0x180023661  test    rax, rax
0x180023664  jz      loc_18002379B
0x18002366a  cmp     [rax+20h], esi
0x18002366d  jnz     loc_18002379B
0x180023673  cmp     [rax+18h], rsi
0x180023677  jnz     short loc_1800236E3
0x180023679  lea     rdx, aProviderNull; "  Provider == NULL"
0x180023680  mov     ecx, 10002h
0x180023685  call    TRACELogPrint
0x18002368a  mov     dword ptr [rbx], 90000019h
0x180023690  jmp     short loc_1800236D0
0x180023692  cmp     esi, 10004h
0x180023698  jb      short loc_1800236AD
0x18002369a  cmp     r14d, 10004h
0x1800236a1  ja      short loc_1800236AD
0x1800236a3  mov     edi, 10004h
0x1800236a8  jmp     loc_1800235F9
0x1800236ad  cmp     r14d, eax
0x1800236b0  ja      short loc_1800236B9
0x1800236b2  mov     edi, eax
0x1800236b4  jmp     loc_1800235F9
0x1800236b9  lea     rdx, aIncompatibleVe; "   Incompatible version"
0x1800236c0  mov     ecx, 10002h
0x1800236c5  call    TRACELogPrint
0x1800236ca  mov     dword ptr [rbx], 90000003h
0x1800236d0  mov     r8d, 1
0x1800236d6  mov     edx, [rbx+8]
0x1800236d9  call    DereferenceObject
0x1800236de  jmp     loc_1800237C8
0x1800236e3  mov     edx, [rax]
0x1800236e5  cmp     r14d, edx
0x1800236e8  ja      loc_18002378F
0x1800236ee  mov     eax, edx
0x1800236f0  cmp     edi, edx
0x1800236f2  cmovbe  eax, edi
0x1800236f5  mov     [rbx+18h], eax
0x1800236f8  mov     rax, [r8+18h]
0x1800236fc  mov     rax, [rax+300h]
0x180023703  mov     rdi, [rsp+58h+arg_18]
0x180023708  test    rax, rax
0x18002370b  jz      short loc_180023720
0x18002370d  mov     r8, rdi
0x180023710  mov     ecx, r15d
0x180023713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023718  mov     [rbx], eax
0x18002371a  test    eax, eax
0x18002371c  jnz     short loc_1800236D0
0x18002371e  jmp     short loc_180023726
0x180023720  xorps   xmm0, xmm0
0x180023723  movups  xmmword ptr [rdi], xmm0
0x180023726  mov     [rbx+1Ch], esi
0x180023729  mov     dword ptr [rbx+20h], 10h
0x180023730  mov     r8d, [rdi]
0x180023733  lea     rdx, aExtensionid0X0; "  ExtensionID0=x%08lx"
0x18002373a  mov     esi, 40002h
0x18002373f  mov     ecx, esi
0x180023741  call    TRACELogPrint
0x180023746  mov     r8d, [rdi+4]
0x18002374a  lea     rdx, aExtensionid1X0; "  ExtensionID1=x%08lx"
0x180023751  mov     ecx, esi
0x180023753  call    TRACELogPrint
0x180023758  mov     r8d, [rdi+8]
0x18002375c  lea     rdx, aExtensionid2X0; "  ExtensionID2=x%08lx"
0x180023763  mov     ecx, esi
0x180023765  call    TRACELogPrint
0x18002376a  mov     r8d, [rdi+0Ch]
0x18002376e  lea     rdx, aExtensionid3X0; "  ExtensionID3=x%08lx"
0x180023775  mov     ecx, esi
0x180023777  call    TRACELogPrint
0x18002377c  mov     rax, [rsp+58h+arg_20]
0x180023784  mov     dword ptr [rax], 4Ch ; 'L'
0x18002378a  jmp     loc_1800236D0
0x18002378f  lea     rdx, aApiVersionTooH; "  API version too high"
0x180023796  jmp     loc_1800236C0
0x18002379b  lea     rdx, aPhoneRemoved; "  phone removed..."
0x1800237a2  mov     ecx, 10002h
0x1800237a7  call    TRACELogPrint
0x1800237ac  mov     dword ptr [rbx], 90000018h
0x1800237b2  jmp     loc_1800236D0
0x1800237b7  mov     dword ptr [rbx], 90000007h
0x1800237bd  jmp     loc_1800236D0
0x1800237c2  mov     dword ptr [rdx], 90000002h
0x1800237c8  mov     r8d, [rbx]
0x1800237cb  lea     rdx, aPhonenegotiate; "phoneNegotiateAPIVersion: exit, result="...
0x1800237d2  mov     ecx, 80002h
0x1800237d7  call    TRACELogPrint
0x1800237dc  mov     rbx, [rsp+58h+arg_0]
0x1800237e1  mov     rsi, [rsp+58h+arg_10]
0x1800237e6  add     rsp, 30h
0x1800237ea  pop     r15
0x1800237ec  pop     r14
0x1800237ee  pop     r13
0x1800237f0  pop     r12
0x1800237f2  pop     rdi
0x1800237f3  retn
```
