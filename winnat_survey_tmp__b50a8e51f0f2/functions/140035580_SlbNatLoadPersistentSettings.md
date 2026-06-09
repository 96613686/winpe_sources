# SlbNatLoadPersistentSettings

- ea: `0x140035580`
- end: `0x140035aef`
- name: `SlbNatLoadPersistentSettings`
- size: `1391`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140035078`

## callees

- `0x14000d7f8`
- `0x14003005c`
- `0x1400300c4`
- `0x1400308ac`
- `0x140032d08`
- `0x140035580`

## import_xrefs

- `NETIO!NsiSetAllParameters` at `0x14003583e`
- `NETIO!NsiSetAllParameters` at `0x1400359d6`
- `NETIO!NsiSetAllParameters` at `0x14003583e`
- `NETIO!NsiSetAllParameters` at `0x1400359d6`
- `NETIO!NsiFreeTable` at `0x140035a98`
- `NETIO!NsiFreeTable` at `0x140035ab2`
- `NETIO!NsiFreeTable` at `0x140035acc`
- `NETIO!NsiFreeTable` at `0x140035a98`
- `NETIO!NsiFreeTable` at `0x140035ab2`
- `NETIO!NsiFreeTable` at `0x140035acc`
- `NETIO!NsiAllocateAndGetTable` at `0x1400356a5`
- `NETIO!NsiAllocateAndGetTable` at `0x1400357b5`
- `NETIO!NsiAllocateAndGetTable` at `0x1400358d6`
- `NETIO!NsiAllocateAndGetTable` at `0x1400356a5`
- `NETIO!NsiAllocateAndGetTable` at `0x1400357b5`
- `NETIO!NsiAllocateAndGetTable` at `0x1400358d6`
- `NETIO!NsiGetAllParameters` at `0x140035605`
- `NETIO!NsiGetAllParameters` at `0x140035605`

## string_xrefs

- `0x14003575b`: `NAT instance creation during startup`
- `0x140035977`: `NAT external address creation during startup`
- `0x140035a6e`: `NAT static mapping creation during startup`

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
  char v7; // r14
  unsigned int i; // esi
  int Instance; // eax
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  const wchar_t *v13; // rax
  int v14; // eax
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // ecx
  unsigned int v18; // edi
  int v19; // edx
  int v20; // r8d
  int v21; // eax
  int v22; // edx
  int v23; // r8d
  int ExternalAddress; // eax
  unsigned int v25; // ecx
  unsigned int v26; // esi
  int v27; // edx
  int v28; // r8d
  int StaticMapping; // eax
  char v31; // [rsp+30h] [rbp-59h]
  int v32; // [rsp+60h] [rbp-29h]
  int v33; // [rsp+60h] [rbp-29h]
  __int64 v34; // [rsp+70h] [rbp-19h] BYREF
  __int64 v35; // [rsp+78h] [rbp-11h] BYREF
  __int64 v36; // [rsp+80h] [rbp-9h] BYREF
  __int64 v37; // [rsp+88h] [rbp-1h] BYREF
  __int64 v38; // [rsp+90h] [rbp+7h] BYREF
  _QWORD v39[9]; // [rsp+98h] [rbp+Fh] BYREF
  unsigned int v40; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v41; // [rsp+F8h] [rbp+6Fh] BYREF
  int v42; // [rsp+100h] [rbp+77h] BYREF
  unsigned int v43; // [rsp+108h] [rbp+7Fh] BYREF

  v42 = -1;
  v43 = 0;
  v40 = 0;
  v41 = 0;
  v39[0] = 0;
  v36 = 0;
  v35 = 0;
  v38 = 0;
  v34 = 0;
  v37 = 0;
  NsiGetAllParameters(0, NPI_MS_WINNAT_MODULEID, 10, 0, 0, &v42, 4, 0, 0, 0, 0);
  v0 = SlbNatSetGlobalParameters(&v42);
  v3 = v0;
  if ( v0 >= 0 )
  {
    Table = NsiAllocateAndGetTable(0, NPI_MS_WINNAT_MODULEID, 6, v39, 80, &v36, 92, 0, 0, 0, 0, &v43, 0);
    v3 = Table;
    if ( Table >= 0 )
    {
      v7 = 0;
      for ( i = 0; i < v43; ++i )
      {
        Instance = SlbNatCreateInstance((NTSTRSAFE_PCWSTR)(v39[0] + 80LL * i));
        v3 = Instance;
        if ( Instance < 0 )
        {
          if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
          {
            v31 = Instance;
            v12 = 1003;
            v13 = L"NAT instance creation during startup";
LABEL_57:
            McTemplateK0qzqq_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
              v10,
              v11,
              v12,
              (__int64)v13,
              i,
              v31);
          }
          goto LABEL_58;
        }
        if ( *(_BYTE *)(92LL * i + v36 + 70) )
          v7 = 1;
      }
      LOBYTE(v32) = 0;
      v14 = NsiAllocateAndGetTable(0, NPI_MS_WINNAT_MODULEID, 7, &v35, 84, &v38, 24, 0, 0, 0, 0, &v40, v32);
      v3 = v14;
      if ( v14 >= 0 )
      {
        v17 = v40;
        if ( v43 || !v40 )
        {
          for ( i = 0; i < v17; ++i )
          {
            ExternalAddress = SlbNatCreateExternalAddress(v35 + 84LL * i);
            v3 = ExternalAddress;
            if ( ExternalAddress < 0 )
            {
              if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
              {
                v31 = ExternalAddress;
                v12 = 1006;
                v13 = L"NAT external address creation during startup";
                goto LABEL_57;
              }
              goto LABEL_58;
            }
            v17 = v40;
          }
        }
        else
        {
          v18 = 0;
          do
            NsiSetAllParameters(0, 3, NPI_MS_WINNAT_MODULEID, 7, v35 + 84LL * v18++, 84, 0, 0);
          while ( v18 < v40 );
          if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
            McTemplateK0qzqq_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
              v19,
              v20,
              1005,
              (__int64)L"Orphaned NAT external addresses in NSI, auto-corrected",
              v40,
              0);
          v40 = 0;
        }
        LOBYTE(v33) = 0;
        v21 = NsiAllocateAndGetTable(0, NPI_MS_WINNAT_MODULEID, 8, &v34, 84, &v37, 84, 0, 0, 0, 0, &v41, v33);
        v3 = v21;
        if ( v21 >= 0 )
        {
          v25 = v41;
          if ( v40 || !v41 || v7 )
          {
            for ( i = 0; i < v25; ++i )
            {
              StaticMapping = SlbNatCreateStaticMapping((wchar_t *)(v34 + 84LL * i));
              v3 = StaticMapping;
              if ( StaticMapping < 0 )
              {
                if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
                {
                  v31 = StaticMapping;
                  v12 = 1009;
                  v13 = L"NAT static mapping creation during startup";
                  goto LABEL_57;
                }
                break;
              }
              v25 = v41;
            }
          }
          else
          {
            v26 = 0;
            do
              NsiSetAllParameters(0, 3, NPI_MS_WINNAT_MODULEID, 8, v34 + 84LL * v26++, 84, 0, 0);
            while ( v26 < v41 );
            if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
              McTemplateK0qzqq_EtwWriteTransfer(
                (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
                v27,
                v28,
                1008,
                (__int64)L"Orphaned NAT static mappings in NSI, auto-corrected",
                v41,
                0);
            v41 = 0;
          }
        }
        else if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
        {
          McTemplateK0qzqq_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
            v22,
            v23,
            1007,
            (__int64)L"Persistent NAT static mapping enumeration",
            0,
            v21);
        }
      }
      else if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
      {
        McTemplateK0qzqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
          v15,
          v16,
          1004,
          (__int64)L"Persistent NAT external address enumeration",
          0,
          v14);
      }
    }
    else if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
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
  else if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
  {
    McTemplateK0qzqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      v1,
      v2,
      1001,
      (__int64)L"Global parameters",
      v42,
      v0);
  }
LABEL_58:
  NsiFreeTable(v34, v37, 0, 0);
  NsiFreeTable(v35, v38, 0, 0);
  NsiFreeTable(v39[0], v36, 0, 0);
  return v3;
}

```

## disassembly

```asm
0x140035580  push    rbp
0x140035582  push    rbx
0x140035583  push    rsi
0x140035584  push    rdi
0x140035585  push    r12
0x140035587  push    r13
0x140035589  push    r14
0x14003558b  push    r15
0x14003558d  lea     rbp, [rsp-1Fh]
0x140035592  sub     rsp, 0A8h
0x140035599  xor     r12d, r12d
0x14003559c  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x1400355a3  mov     [rsp+0E0h+var_90], r12d
0x1400355a8  lea     rax, [rbp+57h+arg_10]
0x1400355ac  mov     [rsp+0E0h+var_98], r12
0x1400355b1  lea     r13, NPI_MS_WINNAT_MODULEID
0x1400355b8  mov     [rsp+0E0h+var_A0], r12d
0x1400355bd  xor     r9d, r9d
0x1400355c0  mov     [rsp+0E0h+var_A8], r12
0x1400355c5  lea     r8d, [r12+0Ah]
0x1400355ca  mov     dword ptr [rsp+0E0h+var_B0], 4
0x1400355d2  mov     rdx, r13
0x1400355d5  mov     [rsp+0E0h+var_B8], rax
0x1400355da  xor     ecx, ecx
0x1400355dc  mov     dword ptr [rsp+0E0h+var_C0], r12d
0x1400355e1  mov     [rbp+57h+arg_18], r12d
0x1400355e5  mov     [rbp+57h+arg_0], r12d
0x1400355e9  mov     [rbp+57h+arg_8], r12d
0x1400355ed  mov     [rbp+57h+var_48], r12
0x1400355f1  mov     [rbp+57h+var_60], r12
0x1400355f5  mov     [rbp+57h+var_68], r12
0x1400355f9  mov     [rbp+57h+var_50], r12
0x1400355fd  mov     [rbp+57h+var_70], r12
0x140035601  mov     [rbp+57h+var_58], r12
0x140035605  call    cs:__imp_NsiGetAllParameters
0x14003560c  nop     dword ptr [rax+rax+00h]
0x140035611  lea     rcx, [rbp+57h+arg_10]
0x140035615  call    SlbNatSetGlobalParameters
0x14003561a  mov     edi, eax
0x14003561c  test    eax, eax
0x14003561e  jns     short loc_14003565B
0x140035620  lea     ebx, [r12+1]
0x140035625  cmp     cs:dword_140026104, ebx
0x14003562b  jnz     loc_140035A8A
0x140035631  test    cs:byte_140026BED, 10h
0x140035638  jz      loc_140035A8A
0x14003563e  mov     ecx, [rbp+57h+arg_10]
0x140035641  mov     r9d, 3E9h
0x140035647  mov     dword ptr [rsp+0E0h+var_B0], eax
0x14003564b  lea     rax, aGlobalParamete; "Global parameters"
0x140035652  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x140035656  jmp     loc_140035A79
0x14003565b  mov     byte ptr [rsp+0E0h+var_80], r12b
0x140035660  lea     rax, [rbp+57h+arg_18]
0x140035664  mov     [rsp+0E0h+var_88], rax
0x140035669  lea     r9, [rbp+57h+var_48]
0x14003566d  mov     [rsp+0E0h+var_90], r12d
0x140035672  lea     rax, [rbp+57h+var_60]
0x140035676  mov     [rsp+0E0h+var_98], r12
0x14003567b  mov     r8d, 6
0x140035681  mov     [rsp+0E0h+var_A0], r12d
0x140035686  mov     rdx, r13
0x140035689  mov     [rsp+0E0h+var_A8], r12
0x14003568e  xor     ecx, ecx
0x140035690  mov     dword ptr [rsp+0E0h+var_B0], 5Ch ; '\'
0x140035698  mov     [rsp+0E0h+var_B8], rax
0x14003569d  mov     dword ptr [rsp+0E0h+var_C0], 50h ; 'P'
0x1400356a5  call    cs:__imp_NsiAllocateAndGetTable
0x1400356ac  nop     dword ptr [rax+rax+00h]
0x1400356b1  mov     edi, eax
0x1400356b3  mov     ebx, 1
0x1400356b8  test    eax, eax
0x1400356ba  jns     short loc_1400356F0
0x1400356bc  cmp     cs:dword_140026104, ebx
0x1400356c2  jnz     loc_140035A8A
0x1400356c8  test    cs:byte_140026BED, 10h
0x1400356cf  jz      loc_140035A8A
0x1400356d5  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1400356d9  mov     r9d, 3EAh
0x1400356df  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x1400356e4  lea     rax, aPersistentNatI; "Persistent NAT instance enumeration"
0x1400356eb  jmp     loc_140035A79
0x1400356f0  mov     rcx, [rbp+57h+var_60]
0x1400356f4  mov     r14b, r12b
0x1400356f7  mov     esi, r12d
0x1400356fa  cmp     esi, [rbp+57h+arg_18]
0x1400356fd  jnb     short loc_140035767
0x1400356ff  mov     eax, esi
0x140035701  mov     r8b, bl
0x140035704  imul    r15, rax, 5Ch ; '\'
0x140035708  lea     rdx, [r15+rcx]
0x14003570c  lea     rcx, [rax+rax*4]
0x140035710  shl     rcx, 4
0x140035714  add     rcx, [rbp+57h+var_48]; pszSrc
0x140035718  call    SlbNatCreateInstance
0x14003571d  mov     edi, eax
0x14003571f  test    eax, eax
0x140035721  js      short loc_140035738
0x140035723  mov     rcx, [rbp+57h+var_60]
0x140035727  movzx   r14d, r14b
0x14003572b  cmp     [r15+rcx+46h], r12b
0x140035730  cmovnz  r14d, ebx
0x140035734  add     esi, ebx
0x140035736  jmp     short loc_1400356FA
0x140035738  cmp     cs:dword_140026104, ebx
0x14003573e  jnz     loc_140035A8A
0x140035744  test    cs:byte_140026BED, 10h
0x14003574b  jz      loc_140035A8A
0x140035751  mov     dword ptr [rsp+0E0h+var_B0], eax
0x140035755  mov     r9d, 3EBh
0x14003575b  lea     rax, aNatInstanceCre; "NAT instance creation during startup"
0x140035762  jmp     loc_140035A75
0x140035767  mov     byte ptr [rsp+0E0h+var_80], r12b
0x14003576c  lea     rax, [rbp+57h+arg_0]
0x140035770  mov     [rsp+0E0h+var_88], rax
0x140035775  lea     r9, [rbp+57h+var_68]
0x140035779  mov     [rsp+0E0h+var_90], r12d
0x14003577e  lea     rax, [rbp+57h+var_50]
0x140035782  mov     [rsp+0E0h+var_98], r12
0x140035787  mov     r15d, 54h ; 'T'
0x14003578d  mov     [rsp+0E0h+var_A0], r12d
0x140035792  mov     rdx, r13
0x140035795  mov     [rsp+0E0h+var_A8], r12
0x14003579a  xor     ecx, ecx
0x14003579c  mov     dword ptr [rsp+0E0h+var_B0], 18h
0x1400357a4  mov     [rsp+0E0h+var_B8], rax
0x1400357a9  lea     esi, [r15-4Dh]
0x1400357ad  mov     r8d, esi
0x1400357b0  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x1400357b5  call    cs:__imp_NsiAllocateAndGetTable
0x1400357bc  nop     dword ptr [rax+rax+00h]
0x1400357c1  mov     edi, eax
0x1400357c3  test    eax, eax
0x1400357c5  jns     short loc_1400357FB
0x1400357c7  cmp     cs:dword_140026104, ebx
0x1400357cd  jnz     loc_140035A8A
0x1400357d3  test    cs:byte_140026BED, 10h
0x1400357da  jz      loc_140035A8A
0x1400357e0  mov     dword ptr [rsp+0E0h+var_B0], eax
0x1400357e4  mov     r9d, 3ECh
0x1400357ea  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x1400357ef  lea     rax, aPersistentNatE; "Persistent NAT external address enumera"...
0x1400357f6  jmp     loc_140035A79
0x1400357fb  mov     ecx, [rbp+57h+arg_0]
0x1400357fe  cmp     [rbp+57h+arg_18], r12d
0x140035802  jnz     loc_140035920
0x140035808  test    ecx, ecx
0x14003580a  jz      loc_140035920
0x140035810  mov     edi, r12d
0x140035813  mov     dword ptr [rsp+0E0h+var_A8], r12d
0x140035818  mov     r9d, esi
0x14003581b  mov     eax, edi
0x14003581d  mov     r8, r13
0x140035820  imul    rcx, rax, 54h ; 'T'
0x140035824  mov     [rsp+0E0h+var_B0], r12
0x140035829  mov     edx, 3
0x14003582e  add     rcx, [rbp+57h+var_68]
0x140035832  mov     dword ptr [rsp+0E0h+var_B8], r15d
0x140035837  mov     [rsp+0E0h+var_C0], rcx
0x14003583c  xor     ecx, ecx
0x14003583e  call    cs:__imp_NsiSetAllParameters
0x140035845  nop     dword ptr [rax+rax+00h]
0x14003584a  mov     ecx, [rbp+57h+arg_0]
0x14003584d  add     edi, ebx
0x14003584f  cmp     edi, ecx
0x140035851  jb      short loc_140035813
0x140035853  cmp     cs:dword_140026104, ebx
0x140035859  jnz     short loc_14003588B
0x14003585b  test    cs:byte_140026BED, 10h
0x140035862  jz      short loc_14003588B
0x140035864  mov     dword ptr [rsp+0E0h+var_B0], r12d
0x140035869  lea     rax, aOrphanedNatExt; "Orphaned NAT external addresses in NSI,"...
0x140035870  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x140035874  mov     r9d, 3EDh
0x14003587a  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140035881  mov     [rsp+0E0h+var_C0], rax
0x140035886  call    McTemplateK0qzqq_EtwWriteTransfer
0x14003588b  mov     [rbp+57h+arg_0], r12d
0x14003588f  mov     byte ptr [rsp+0E0h+var_80], r12b
0x140035894  lea     rax, [rbp+57h+arg_8]
0x140035898  mov     [rsp+0E0h+var_88], rax
0x14003589d  lea     r9, [rbp+57h+var_70]
0x1400358a1  mov     [rsp+0E0h+var_90], r12d
0x1400358a6  lea     rax, [rbp+57h+var_58]
0x1400358aa  mov     [rsp+0E0h+var_98], r12
0x1400358af  mov     rdx, r13
0x1400358b2  mov     [rsp+0E0h+var_A0], r12d
0x1400358b7  xor     ecx, ecx
0x1400358b9  mov     [rsp+0E0h+var_A8], r12
0x1400358be  mov     dword ptr [rsp+0E0h+var_B0], r15d
0x1400358c3  mov     [rsp+0E0h+var_B8], rax
0x1400358c8  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x1400358cd  mov     r15d, 8
0x1400358d3  mov     r8d, r15d
0x1400358d6  call    cs:__imp_NsiAllocateAndGetTable
0x1400358dd  nop     dword ptr [rax+rax+00h]
0x1400358e2  mov     edi, eax
0x1400358e4  test    eax, eax
0x1400358e6  jns     loc_140035983
0x1400358ec  cmp     cs:dword_140026104, ebx
0x1400358f2  jnz     loc_140035A8A
0x1400358f8  test    cs:byte_140026BED, 10h
0x1400358ff  jz      loc_140035A8A
0x140035905  mov     dword ptr [rsp+0E0h+var_B0], eax
0x140035909  mov     r9d, 3EFh
0x14003590f  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x140035914  lea     rax, aPersistentNatS; "Persistent NAT static mapping enumerati"...
0x14003591b  jmp     loc_140035A79
0x140035920  mov     esi, r12d
0x140035923  cmp     esi, ecx
0x140035925  jnb     loc_14003588F
0x14003592b  mov     rax, [rbp+57h+var_50]
0x14003592f  mov     r8d, esi
0x140035932  lea     rcx, [r8+r8*2]
0x140035936  lea     rdx, [rax+rcx*8]
0x14003593a  imul    rcx, r8, 54h ; 'T'
0x14003593e  add     rcx, [rbp+57h+var_68]
0x140035942  call    SlbNatCreateExternalAddress
0x140035947  mov     edi, eax
0x140035949  test    eax, eax
0x14003594b  js      short loc_140035954
0x14003594d  mov     ecx, [rbp+57h+arg_0]
0x140035950  add     esi, ebx
0x140035952  jmp     short loc_140035923
0x140035954  cmp     cs:dword_140026104, ebx
0x14003595a  jnz     loc_140035A8A
0x140035960  test    cs:byte_140026BED, 10h
0x140035967  jz      loc_140035A8A
0x14003596d  mov     dword ptr [rsp+0E0h+var_B0], eax
0x140035971  mov     r9d, 3EEh
0x140035977  lea     rax, aNatExternalAdd; "NAT external address creation during st"...
0x14003597e  jmp     loc_140035A75
0x140035983  mov     ecx, [rbp+57h+arg_8]
0x140035986  cmp     [rbp+57h+arg_0], r12d
0x14003598a  jnz     loc_140035A29
0x140035990  test    ecx, ecx
0x140035992  jz      loc_140035A29
0x140035998  test    r14b, r14b
0x14003599b  jnz     loc_140035A29
0x1400359a1  mov     esi, r12d
0x1400359a4  test    ecx, ecx
0x1400359a6  jz      short loc_1400359EB
0x1400359a8  mov     dword ptr [rsp+0E0h+var_A8], r12d
0x1400359ad  mov     r9d, r15d
0x1400359b0  mov     eax, esi
0x1400359b2  mov     r8, r13
0x1400359b5  imul    rcx, rax, 54h ; 'T'
0x1400359b9  mov     [rsp+0E0h+var_B0], r12
0x1400359be  mov     edx, 3
0x1400359c3  add     rcx, [rbp+57h+var_70]
0x1400359c7  mov     dword ptr [rsp+0E0h+var_B8], 54h ; 'T'
0x1400359cf  mov     [rsp+0E0h+var_C0], rcx
0x1400359d4  xor     ecx, ecx
0x1400359d6  call    cs:__imp_NsiSetAllParameters
0x1400359dd  nop     dword ptr [rax+rax+00h]
0x1400359e2  mov     ecx, [rbp+57h+arg_8]
0x1400359e5  add     esi, ebx
0x1400359e7  cmp     esi, ecx
0x1400359e9  jb      short loc_1400359A8
0x1400359eb  cmp     cs:dword_140026104, ebx
0x1400359f1  jnz     short loc_140035A23
0x1400359f3  test    cs:byte_140026BED, 10h
0x1400359fa  jz      short loc_140035A23
0x1400359fc  mov     dword ptr [rsp+0E0h+var_B0], r12d
0x140035a01  lea     rax, aOrphanedNatSta; "Orphaned NAT static mappings in NSI, au"...
0x140035a08  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x140035a0c  mov     r9d, 3F0h
0x140035a12  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140035a19  mov     [rsp+0E0h+var_C0], rax
0x140035a1e  call    McTemplateK0qzqq_EtwWriteTransfer
0x140035a23  mov     [rbp+57h+arg_8], r12d
0x140035a27  jmp     short loc_140035A8A
0x140035a29  mov     esi, r12d
0x140035a2c  cmp     esi, ecx
0x140035a2e  jnb     short loc_140035A8A
0x140035a30  mov     rdx, [rbp+57h+var_58]
0x140035a34  mov     eax, esi
0x140035a36  imul    rcx, rax, 54h ; 'T'
0x140035a3a  add     rdx, rcx
0x140035a3d  add     rcx, [rbp+57h+var_70]; Str2
0x140035a41  call    SlbNatCreateStaticMapping
0x140035a46  mov     edi, eax
0x140035a48  test    eax, eax
0x140035a4a  js      short loc_140035A53
0x140035a4c  mov     ecx, [rbp+57h+arg_8]
0x140035a4f  add     esi, ebx
0x140035a51  jmp     short loc_140035A2C
0x140035a53  cmp     cs:dword_140026104, ebx
0x140035a59  jnz     short loc_140035A8A
0x140035a5b  test    cs:byte_140026BED, 10h
0x140035a62  jz      short loc_140035A8A
0x140035a64  mov     dword ptr [rsp+0E0h+var_B0], eax
0x140035a68  mov     r9d, 3F1h
0x140035a6e  lea     rax, aNatStaticMappi; "NAT static mapping creation during star"...
0x140035a75  mov     dword ptr [rsp+0E0h+var_B8], esi
0x140035a79  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x140035a80  mov     [rsp+0E0h+var_C0], rax
0x140035a85  call    McTemplateK0qzqq_EtwWriteTransfer
0x140035a8a  mov     rdx, [rbp+57h+var_58]
0x140035a8e  xor     r9d, r9d
  ... truncated ...
```
