# SlbNatLoadPersistentSettings

- ea: `0x140036580`
- end: `0x140036aef`
- name: `SlbNatLoadPersistentSettings`
- size: `1391`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140036078`

## callees

- `0x14000d7c8`
- `0x14003118c`
- `0x1400311f4`
- `0x1400319dc`
- `0x140033e38`
- `0x140036580`

## import_xrefs

- `NETIO!NsiSetAllParameters` at `0x14003683e`
- `NETIO!NsiSetAllParameters` at `0x1400369d6`
- `NETIO!NsiSetAllParameters` at `0x14003683e`
- `NETIO!NsiSetAllParameters` at `0x1400369d6`
- `NETIO!NsiFreeTable` at `0x140036a98`
- `NETIO!NsiFreeTable` at `0x140036ab2`
- `NETIO!NsiFreeTable` at `0x140036acc`
- `NETIO!NsiFreeTable` at `0x140036a98`
- `NETIO!NsiFreeTable` at `0x140036ab2`
- `NETIO!NsiFreeTable` at `0x140036acc`
- `NETIO!NsiAllocateAndGetTable` at `0x1400366a5`
- `NETIO!NsiAllocateAndGetTable` at `0x1400367b5`
- `NETIO!NsiAllocateAndGetTable` at `0x1400368d6`
- `NETIO!NsiAllocateAndGetTable` at `0x1400366a5`
- `NETIO!NsiAllocateAndGetTable` at `0x1400367b5`
- `NETIO!NsiAllocateAndGetTable` at `0x1400368d6`
- `NETIO!NsiGetAllParameters` at `0x140036605`
- `NETIO!NsiGetAllParameters` at `0x140036605`

## string_xrefs

- `0x14003675b`: `NAT instance creation during startup`
- `0x140036977`: `NAT external address creation during startup`
- `0x140036a6e`: `NAT static mapping creation during startup`

## pseudocode

```c
__int64 SlbNatLoadPersistentSettings()
{
  int v0; // eax
  int v1; // edx
  int v2; // r8d
  unsigned int v3; // edi
  int Table; // eax
  int v5; // edx
  int v6; // r8d
  __int64 v7; // rcx
  char v8; // r14
  unsigned int i; // esi
  __int64 v10; // r15
  int Instance; // eax
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  const wchar_t *v15; // rax
  int v16; // eax
  int v17; // edx
  int v18; // r8d
  unsigned int v19; // ecx
  unsigned int v20; // edi
  int v21; // edx
  int v22; // r8d
  int v23; // eax
  int v24; // edx
  int v25; // r8d
  int ExternalAddress; // eax
  unsigned int v27; // ecx
  unsigned int v28; // esi
  int v29; // edx
  int v30; // r8d
  int StaticMapping; // eax
  char v33; // [rsp+30h] [rbp-59h]
  int v34; // [rsp+60h] [rbp-29h]
  int v35; // [rsp+60h] [rbp-29h]
  __int64 v36; // [rsp+70h] [rbp-19h] BYREF
  __int64 v37; // [rsp+78h] [rbp-11h] BYREF
  __int64 v38; // [rsp+80h] [rbp-9h] BYREF
  __int64 v39; // [rsp+88h] [rbp-1h] BYREF
  __int64 v40; // [rsp+90h] [rbp+7h] BYREF
  _QWORD v41[9]; // [rsp+98h] [rbp+Fh] BYREF
  unsigned int v42; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v43; // [rsp+F8h] [rbp+6Fh] BYREF
  int v44; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v45; // [rsp+108h] [rbp+7Fh] BYREF

  v44 = -1;
  v45 = 0;
  v42 = 0;
  v43 = 0;
  v41[0] = 0;
  v38 = 0;
  v37 = 0;
  v40 = 0;
  v36 = 0;
  v39 = 0;
  NsiGetAllParameters(0, NPI_MS_WINNAT_MODULEID, 10, 0, 0, &v44, 4, 0, 0, 0, 0);
  v0 = SlbNatSetGlobalParameters(&v44);
  v3 = v0;
  if ( v0 >= 0 )
  {
    Table = NsiAllocateAndGetTable(0, NPI_MS_WINNAT_MODULEID, 6, v41, 80, &v38, 92, 0, 0, 0, 0, &v45, 0);
    v3 = Table;
    if ( Table >= 0 )
    {
      v7 = v38;
      v8 = 0;
      for ( i = 0; i < v45; ++i )
      {
        v10 = 92LL * i;
        Instance = SlbNatCreateInstance((NTSTRSAFE_PCWSTR)(v41[0] + 80LL * i), (int *)(v10 + v7), 1);
        v3 = Instance;
        if ( Instance < 0 )
        {
          if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
          {
            v33 = Instance;
            v14 = 1003;
            v15 = L"NAT instance creation during startup";
LABEL_57:
            McTemplateK0qzqq_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
              v12,
              v13,
              v14,
              (__int64)v15,
              i,
              v33);
          }
          goto LABEL_58;
        }
        v7 = v38;
        if ( *(_BYTE *)(v10 + v38 + 70) )
          v8 = 1;
      }
      LOBYTE(v34) = 0;
      v16 = NsiAllocateAndGetTable(0, NPI_MS_WINNAT_MODULEID, 7, &v37, 84, &v40, 24, 0, 0, 0, 0, &v42, v34);
      v3 = v16;
      if ( v16 >= 0 )
      {
        v19 = v42;
        if ( v45 || !v42 )
        {
          for ( i = 0; i < v19; ++i )
          {
            ExternalAddress = SlbNatCreateExternalAddress(v37 + 84LL * i);
            v3 = ExternalAddress;
            if ( ExternalAddress < 0 )
            {
              if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
              {
                v33 = ExternalAddress;
                v14 = 1006;
                v15 = L"NAT external address creation during startup";
                goto LABEL_57;
              }
              goto LABEL_58;
            }
            v19 = v42;
          }
        }
        else
        {
          v20 = 0;
          do
            NsiSetAllParameters(0, 3, NPI_MS_WINNAT_MODULEID, 7, v37 + 84LL * v20++, 84, 0, 0);
          while ( v20 < v42 );
          if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
            McTemplateK0qzqq_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
              v21,
              v22,
              1005,
              (__int64)L"Orphaned NAT external addresses in NSI, auto-corrected",
              v42,
              0);
          v42 = 0;
        }
        LOBYTE(v35) = 0;
        v23 = NsiAllocateAndGetTable(0, NPI_MS_WINNAT_MODULEID, 8, &v36, 84, &v39, 84, 0, 0, 0, 0, &v43, v35);
        v3 = v23;
        if ( v23 >= 0 )
        {
          v27 = v43;
          if ( v42 || !v43 || v8 )
          {
            for ( i = 0; i < v27; ++i )
            {
              StaticMapping = SlbNatCreateStaticMapping((wchar_t *)(v36 + 84LL * i), 84LL * i + v39);
              v3 = StaticMapping;
              if ( StaticMapping < 0 )
              {
                if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
                {
                  v33 = StaticMapping;
                  v14 = 1009;
                  v15 = L"NAT static mapping creation during startup";
                  goto LABEL_57;
                }
                break;
              }
              v27 = v43;
            }
          }
          else
          {
            v28 = 0;
            do
              NsiSetAllParameters(0, 3, NPI_MS_WINNAT_MODULEID, 8, v36 + 84LL * v28++, 84, 0, 0);
            while ( v28 < v43 );
            if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
              McTemplateK0qzqq_EtwWriteTransfer(
                (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
                v29,
                v30,
                1008,
                (__int64)L"Orphaned NAT static mappings in NSI, auto-corrected",
                v43,
                0);
            v43 = 0;
          }
        }
        else if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
        {
          McTemplateK0qzqq_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
            v24,
            v25,
            1007,
            (__int64)L"Persistent NAT static mapping enumeration",
            0,
            v23);
        }
      }
      else if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
      {
        McTemplateK0qzqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
          v17,
          v18,
          1004,
          (__int64)L"Persistent NAT external address enumeration",
          0,
          v16);
      }
    }
    else if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
    {
      McTemplateK0qzqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        v5,
        v6,
        1002,
        (__int64)L"Persistent NAT instance enumeration",
        0,
        Table);
    }
  }
  else if ( dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
  {
    McTemplateK0qzqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      v1,
      v2,
      1001,
      (__int64)L"Global parameters",
      v44,
      v0);
  }
LABEL_58:
  NsiFreeTable(v36, v39, 0, 0);
  NsiFreeTable(v37, v40, 0, 0);
  NsiFreeTable(v41[0], v38, 0, 0);
  return v3;
}

```

## disassembly

```asm
0x140036580  push    rbp
0x140036582  push    rbx
0x140036583  push    rsi
0x140036584  push    rdi
0x140036585  push    r12
0x140036587  push    r13
0x140036589  push    r14
0x14003658b  push    r15
0x14003658d  lea     rbp, [rsp-1Fh]
0x140036592  sub     rsp, 0A8h
0x140036599  xor     r12d, r12d
0x14003659c  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x1400365a3  mov     [rsp+0E0h+var_90], r12d
0x1400365a8  lea     rax, [rbp+57h+arg_10]
0x1400365ac  mov     [rsp+0E0h+var_98], r12
0x1400365b1  lea     r13, NPI_MS_WINNAT_MODULEID
0x1400365b8  mov     [rsp+0E0h+var_A0], r12d
0x1400365bd  xor     r9d, r9d
0x1400365c0  mov     [rsp+0E0h+var_A8], r12
0x1400365c5  lea     r8d, [r12+0Ah]
0x1400365ca  mov     dword ptr [rsp+0E0h+var_B0], 4
0x1400365d2  mov     rdx, r13
0x1400365d5  mov     [rsp+0E0h+var_B8], rax
0x1400365da  xor     ecx, ecx
0x1400365dc  mov     dword ptr [rsp+0E0h+var_C0], r12d
0x1400365e1  mov     [rbp+57h+arg_18], r12d
0x1400365e5  mov     [rbp+57h+arg_0], r12d
0x1400365e9  mov     [rbp+57h+arg_8], r12d
0x1400365ed  mov     [rbp+57h+var_48], r12
0x1400365f1  mov     [rbp+57h+var_60], r12
0x1400365f5  mov     [rbp+57h+var_68], r12
0x1400365f9  mov     [rbp+57h+var_50], r12
0x1400365fd  mov     [rbp+57h+var_70], r12
0x140036601  mov     [rbp+57h+var_58], r12
0x140036605  call    cs:__imp_NsiGetAllParameters
0x14003660c  nop     dword ptr [rax+rax+00h]
0x140036611  lea     rcx, [rbp+57h+arg_10]
0x140036615  call    SlbNatSetGlobalParameters
0x14003661a  mov     edi, eax
0x14003661c  test    eax, eax
0x14003661e  jns     short loc_14003665B
0x140036620  lea     ebx, [r12+1]
0x140036625  cmp     cs:dword_140027104, ebx
0x14003662b  jnz     loc_140036A8A
0x140036631  test    cs:byte_140027BED, 10h
0x140036638  jz      loc_140036A8A
0x14003663e  mov     ecx, [rbp+57h+arg_10]
0x140036641  mov     r9d, 3E9h
0x140036647  mov     dword ptr [rsp+0E0h+var_B0], eax
0x14003664b  lea     rax, aGlobalParamete; "Global parameters"
0x140036652  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x140036656  jmp     loc_140036A79
0x14003665b  mov     byte ptr [rsp+0E0h+var_80], r12b
0x140036660  lea     rax, [rbp+57h+arg_18]
0x140036664  mov     [rsp+0E0h+var_88], rax
0x140036669  lea     r9, [rbp+57h+var_48]
0x14003666d  mov     [rsp+0E0h+var_90], r12d
0x140036672  lea     rax, [rbp+57h+var_60]
0x140036676  mov     [rsp+0E0h+var_98], r12
0x14003667b  mov     r8d, 6
0x140036681  mov     [rsp+0E0h+var_A0], r12d
0x140036686  mov     rdx, r13
0x140036689  mov     [rsp+0E0h+var_A8], r12
0x14003668e  xor     ecx, ecx
0x140036690  mov     dword ptr [rsp+0E0h+var_B0], 5Ch ; '\'
0x140036698  mov     [rsp+0E0h+var_B8], rax
0x14003669d  mov     dword ptr [rsp+0E0h+var_C0], 50h ; 'P'
0x1400366a5  call    cs:__imp_NsiAllocateAndGetTable
0x1400366ac  nop     dword ptr [rax+rax+00h]
0x1400366b1  mov     edi, eax
0x1400366b3  mov     ebx, 1
0x1400366b8  test    eax, eax
0x1400366ba  jns     short loc_1400366F0
0x1400366bc  cmp     cs:dword_140027104, ebx
0x1400366c2  jnz     loc_140036A8A
0x1400366c8  test    cs:byte_140027BED, 10h
0x1400366cf  jz      loc_140036A8A
0x1400366d5  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1400366d9  mov     r9d, 3EAh
0x1400366df  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x1400366e4  lea     rax, aPersistentNatI; "Persistent NAT instance enumeration"
0x1400366eb  jmp     loc_140036A79
0x1400366f0  mov     rcx, [rbp+57h+var_60]
0x1400366f4  mov     r14b, r12b
0x1400366f7  mov     esi, r12d
0x1400366fa  cmp     esi, [rbp+57h+arg_18]
0x1400366fd  jnb     short loc_140036767
0x1400366ff  mov     eax, esi
0x140036701  mov     r8b, bl
0x140036704  imul    r15, rax, 5Ch ; '\'
0x140036708  lea     rdx, [r15+rcx]
0x14003670c  lea     rcx, [rax+rax*4]
0x140036710  shl     rcx, 4
0x140036714  add     rcx, [rbp+57h+var_48]; pszSrc
0x140036718  call    SlbNatCreateInstance
0x14003671d  mov     edi, eax
0x14003671f  test    eax, eax
0x140036721  js      short loc_140036738
0x140036723  mov     rcx, [rbp+57h+var_60]
0x140036727  movzx   r14d, r14b
0x14003672b  cmp     [r15+rcx+46h], r12b
0x140036730  cmovnz  r14d, ebx
0x140036734  add     esi, ebx
0x140036736  jmp     short loc_1400366FA
0x140036738  cmp     cs:dword_140027104, ebx
0x14003673e  jnz     loc_140036A8A
0x140036744  test    cs:byte_140027BED, 10h
0x14003674b  jz      loc_140036A8A
0x140036751  mov     dword ptr [rsp+0E0h+var_B0], eax
0x140036755  mov     r9d, 3EBh
0x14003675b  lea     rax, aNatInstanceCre; "NAT instance creation during startup"
0x140036762  jmp     loc_140036A75
0x140036767  mov     byte ptr [rsp+0E0h+var_80], r12b
0x14003676c  lea     rax, [rbp+57h+arg_0]
0x140036770  mov     [rsp+0E0h+var_88], rax
0x140036775  lea     r9, [rbp+57h+var_68]
0x140036779  mov     [rsp+0E0h+var_90], r12d
0x14003677e  lea     rax, [rbp+57h+var_50]
0x140036782  mov     [rsp+0E0h+var_98], r12
0x140036787  mov     r15d, 54h ; 'T'
0x14003678d  mov     [rsp+0E0h+var_A0], r12d
0x140036792  mov     rdx, r13
0x140036795  mov     [rsp+0E0h+var_A8], r12
0x14003679a  xor     ecx, ecx
0x14003679c  mov     dword ptr [rsp+0E0h+var_B0], 18h
0x1400367a4  mov     [rsp+0E0h+var_B8], rax
0x1400367a9  lea     esi, [r15-4Dh]
0x1400367ad  mov     r8d, esi
0x1400367b0  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x1400367b5  call    cs:__imp_NsiAllocateAndGetTable
0x1400367bc  nop     dword ptr [rax+rax+00h]
0x1400367c1  mov     edi, eax
0x1400367c3  test    eax, eax
0x1400367c5  jns     short loc_1400367FB
0x1400367c7  cmp     cs:dword_140027104, ebx
0x1400367cd  jnz     loc_140036A8A
0x1400367d3  test    cs:byte_140027BED, 10h
0x1400367da  jz      loc_140036A8A
0x1400367e0  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1400367e4  mov     r9d, 3ECh
0x1400367ea  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x1400367ef  lea     rax, aPersistentNatE; "Persistent NAT external address enumera"...
0x1400367f6  jmp     loc_140036A79
0x1400367fb  mov     ecx, [rbp+57h+arg_0]
0x1400367fe  cmp     [rbp+57h+arg_18], r12d
0x140036802  jnz     loc_140036920
0x140036808  test    ecx, ecx
0x14003680a  jz      loc_140036920
0x140036810  mov     edi, r12d
0x140036813  mov     dword ptr [rsp+0E0h+var_A8], r12d
0x140036818  mov     r9d, esi
0x14003681b  mov     eax, edi
0x14003681d  mov     r8, r13
0x140036820  imul    rcx, rax, 54h ; 'T'
0x140036824  mov     [rsp+0E0h+var_B0], r12
0x140036829  mov     edx, 3
0x14003682e  add     rcx, [rbp+57h+var_68]
0x140036832  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x140036837  mov     [rsp+0E0h+var_C0], rcx
0x14003683c  xor     ecx, ecx
0x14003683e  call    cs:__imp_NsiSetAllParameters
0x140036845  nop     dword ptr [rax+rax+00h]
0x14003684a  mov     ecx, [rbp+57h+arg_0]
0x14003684d  add     edi, ebx
0x14003684f  cmp     edi, ecx
0x140036851  jb      short loc_140036813
0x140036853  cmp     cs:dword_140027104, ebx
0x140036859  jnz     short loc_14003688B
0x14003685b  test    cs:byte_140027BED, 10h
0x140036862  jz      short loc_14003688B
0x140036864  mov     dword ptr [rsp+0E0h+var_B0], r12d
0x140036869  lea     rax, aOrphanedNatExt; "Orphaned NAT external addresses in NSI,"...
0x140036870  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x140036874  mov     r9d, 3EDh
0x14003687a  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140036881  mov     [rsp+0E0h+var_C0], rax
0x140036886  call    McTemplateK0qzqq_EtwWriteTransfer
0x14003688b  mov     [rbp+57h+arg_0], r12d
0x14003688f  mov     byte ptr [rsp+0E0h+var_80], r12b
0x140036894  lea     rax, [rbp+57h+arg_8]
0x140036898  mov     [rsp+0E0h+var_88], rax
0x14003689d  lea     r9, [rbp+57h+var_70]
0x1400368a1  mov     [rsp+0E0h+var_90], r12d
0x1400368a6  lea     rax, [rbp+57h+var_58]
0x1400368aa  mov     [rsp+0E0h+var_98], r12
0x1400368af  mov     rdx, r13
0x1400368b2  mov     [rsp+0E0h+var_A0], r12d
0x1400368b7  xor     ecx, ecx
0x1400368b9  mov     [rsp+0E0h+var_A8], r12
0x1400368be  mov     dword ptr [rsp+0E0h+var_B0], r15d
0x1400368c3  mov     [rsp+0E0h+var_B8], rax
0x1400368c8  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x1400368cd  mov     r15d, 8
0x1400368d3  mov     r8d, r15d
0x1400368d6  call    cs:__imp_NsiAllocateAndGetTable
0x1400368dd  nop     dword ptr [rax+rax+00h]
0x1400368e2  mov     edi, eax
0x1400368e4  test    eax, eax
0x1400368e6  jns     loc_140036983
0x1400368ec  cmp     cs:dword_140027104, ebx
0x1400368f2  jnz     loc_140036A8A
0x1400368f8  test    cs:byte_140027BED, 10h
0x1400368ff  jz      loc_140036A8A
0x140036905  mov     dword ptr [rsp+0E0h+var_B0], eax
0x140036909  mov     r9d, 3EFh
0x14003690f  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x140036914  lea     rax, aPersistentNatS; "Persistent NAT static mapping enumerati"...
0x14003691b  jmp     loc_140036A79
0x140036920  mov     esi, r12d
0x140036923  cmp     esi, ecx
0x140036925  jnb     loc_14003688F
0x14003692b  mov     rax, [rbp+57h+var_50]
0x14003692f  mov     r8d, esi
0x140036932  lea     rcx, [r8+r8*2]
0x140036936  lea     rdx, [rax+rcx*8]
0x14003693a  imul    rcx, r8, 54h ; 'T'
0x14003693e  add     rcx, [rbp+57h+var_68]
0x140036942  call    SlbNatCreateExternalAddress
0x140036947  mov     edi, eax
0x140036949  test    eax, eax
0x14003694b  js      short loc_140036954
0x14003694d  mov     ecx, [rbp+57h+arg_0]
0x140036950  add     esi, ebx
0x140036952  jmp     short loc_140036923
0x140036954  cmp     cs:dword_140027104, ebx
0x14003695a  jnz     loc_140036A8A
0x140036960  test    cs:byte_140027BED, 10h
0x140036967  jz      loc_140036A8A
0x14003696d  mov     dword ptr [rsp+0E0h+var_B0], eax
0x140036971  mov     r9d, 3EEh
0x140036977  lea     rax, aNatExternalAdd; "NAT external address creation during st"...
0x14003697e  jmp     loc_140036A75
0x140036983  mov     ecx, [rbp+57h+arg_8]
0x140036986  cmp     [rbp+57h+arg_0], r12d
0x14003698a  jnz     loc_140036A29
0x140036990  test    ecx, ecx
0x140036992  jz      loc_140036A29
0x140036998  test    r14b, r14b
0x14003699b  jnz     loc_140036A29
0x1400369a1  mov     esi, r12d
0x1400369a4  test    ecx, ecx
0x1400369a6  jz      short loc_1400369EB
0x1400369a8  mov     dword ptr [rsp+0E0h+var_A8], r12d
0x1400369ad  mov     r9d, r15d
0x1400369b0  mov     eax, esi
0x1400369b2  mov     r8, r13
0x1400369b5  imul    rcx, rax, 54h ; 'T'
0x1400369b9  mov     [rsp+0E0h+var_B0], r12
0x1400369be  mov     edx, 3
0x1400369c3  add     rcx, [rbp+57h+var_70]
0x1400369c7  mov     dword ptr [rsp+0E0h+var_B8], 54h ; 'T'
0x1400369cf  mov     [rsp+0E0h+var_C0], rcx
0x1400369d4  xor     ecx, ecx
0x1400369d6  call    cs:__imp_NsiSetAllParameters
0x1400369dd  nop     dword ptr [rax+rax+00h]
0x1400369e2  mov     ecx, [rbp+57h+arg_8]
0x1400369e5  add     esi, ebx
0x1400369e7  cmp     esi, ecx
0x1400369e9  jb      short loc_1400369A8
0x1400369eb  cmp     cs:dword_140027104, ebx
0x1400369f1  jnz     short loc_140036A23
0x1400369f3  test    cs:byte_140027BED, 10h
0x1400369fa  jz      short loc_140036A23
0x1400369fc  mov     dword ptr [rsp+0E0h+var_B0], r12d
0x140036a01  lea     rax, aOrphanedNatSta; "Orphaned NAT static mappings in NSI, au"...
0x140036a08  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x140036a0c  mov     r9d, 3F0h
0x140036a12  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140036a19  mov     [rsp+0E0h+var_C0], rax
0x140036a1e  call    McTemplateK0qzqq_EtwWriteTransfer
0x140036a23  mov     [rbp+57h+arg_8], r12d
0x140036a27  jmp     short loc_140036A8A
0x140036a29  mov     esi, r12d
0x140036a2c  cmp     esi, ecx
0x140036a2e  jnb     short loc_140036A8A
0x140036a30  mov     rdx, [rbp+57h+var_58]
0x140036a34  mov     eax, esi
0x140036a36  imul    rcx, rax, 54h ; 'T'
0x140036a3a  add     rdx, rcx
0x140036a3d  add     rcx, [rbp+57h+var_70]; Str2
0x140036a41  call    SlbNatCreateStaticMapping
0x140036a46  mov     edi, eax
0x140036a48  test    eax, eax
0x140036a4a  js      short loc_140036A53
0x140036a4c  mov     ecx, [rbp+57h+arg_8]
0x140036a4f  add     esi, ebx
0x140036a51  jmp     short loc_140036A2C
0x140036a53  cmp     cs:dword_140027104, ebx
0x140036a59  jnz     short loc_140036A8A
0x140036a5b  test    cs:byte_140027BED, 10h
0x140036a62  jz      short loc_140036A8A
0x140036a64  mov     dword ptr [rsp+0E0h+var_B0], eax
0x140036a68  mov     r9d, 3F1h
0x140036a6e  lea     rax, aNatStaticMappi; "NAT static mapping creation during star"...
0x140036a75  mov     dword ptr [rsp+0E0h+var_B8], esi
0x140036a79  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140036a80  mov     [rsp+0E0h+var_C0], rax
0x140036a85  call    McTemplateK0qzqq_EtwWriteTransfer
0x140036a8a  mov     rdx, [rbp+57h+var_58]
0x140036a8e  xor     r9d, r9d
  ... truncated ...
```
