# UpdateSyncRootMapSizes(_FILE_ID_EXTD_DIR_INFORMATION *,DIRECTORY_SCAN_FUNC_ARGS *,ScanDirectoryObjectFlag,bool)

- ea: `0x18001d8b0`
- end: `0x18001dc9c`
- name: `?UpdateSyncRootMapSizes@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAUDIRECTORY_SCAN_FUNC_ARGS@@W4ScanDirectoryObjectFlag@@_N@Z`
- size: `1004`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callees

- `0x1800050f0`
- `0x1800152d4`
- `0x180017dc8`
- `0x180018dec`
- `0x18001a2c8`
- `0x18001c968`
- `0x18001d608`
- `0x18001d6c0`
- `0x18001d8b0`
- `0x18001f4a0`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18001da9e`
- `ntdll!RtlEqualUnicodeString` at `0x18001da9e`

## pseudocode

```c
__int64 __fastcall UpdateSyncRootMapSizes(__int64 a1, __int64 a2, int a3)
{
  __int64 v5; // rbx
  int v6; // edx
  int v7; // r8d
  int v8; // edx
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  int v12; // eax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  struct _UNICODE_STRING *v15; // r12
  PCUNICODE_STRING *i; // rsi
  _QWORD *v17; // rax
  unsigned __int16 *v18; // rdx
  USHORT Length; // cx
  unsigned int v20; // r8d
  unsigned int v21; // r9d
  int v22; // esi
  unsigned __int16 v23; // r8
  __int64 v24; // rdx
  _QWORD *v26; // rax
  _QWORD *v27; // rax
  int v28; // eax
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  __int64 v31; // rax
  _QWORD *v32; // rax
  _QWORD *v33; // rax
  int v34; // [rsp+20h] [rbp-50h] BYREF
  UNICODE_STRING String2; // [rsp+28h] [rbp-48h] BYREF
  unsigned __int16 v36[8]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v37[26]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  if ( ((a3 - 8) & 0xFFFFFFF7) != 0 )
  {
    v5 = *(_QWORD *)(a2 + 152);
    if ( a3 == 1 )
    {
      v6 = *(_DWORD *)(a1 + 68);
      if ( (v6 & 0x9000001A) == 0x9000001A )
      {
        v7 = *(_DWORD *)(a1 + 56);
        v8 = v6 & 0x6FFF0FE5;
        if ( v8 == 0 && (v7 & 0x400) != 0 )
        {
          v34 = 16;
LABEL_10:
          v9 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](v5, &v34);
          ++*v9;
          goto LABEL_11;
        }
        if ( v8 != 0 && (v7 & 0x400) != 0 )
        {
          v34 = 20;
          goto LABEL_10;
        }
        if ( (v7 & 0x400) != 0 )
        {
LABEL_11:
          if ( (*(_DWORD *)(a1 + 68) & 0x4000) != 0 )
          {
            v34 = 22;
            v10 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](v5, &v34);
            ++*v10;
          }
          v34 = 0;
          v11 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](v5, &v34);
          ++*v11;
          v12 = *(_DWORD *)(a1 + 56) & 0x100000;
          if ( (*(_DWORD *)(a1 + 56) & 0x80000) != 0 )
          {
            if ( v12 )
              v34 = 14;
            else
              v34 = 11;
          }
          else
          {
            v34 = 12;
            if ( !v12 )
              v34 = 13;
          }
          v13 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](v5, &v34);
          ++*v13;
          if ( (*(_BYTE *)(a1 + 56) & 1) != 0 )
          {
            v34 = 41;
            v14 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](v5, &v34);
            ++*v14;
          }
          return 0;
        }
      }
      v34 = 18;
      goto LABEL_10;
    }
    if ( a3 == 4 )
    {
      if ( (*(_DWORD *)(a1 + 68) & 0x9000001A) == 0x9000001A )
      {
        if ( (*(_DWORD *)(a1 + 68) & 0x6FFF0FE5) != 0 )
        {
          if ( (*(_DWORD *)(a1 + 56) & 0x400) != 0 )
          {
            v34 = 19;
            goto LABEL_42;
          }
        }
        else if ( (*(_DWORD *)(a1 + 56) & 0x400) != 0 )
        {
          v34 = 15;
          goto LABEL_42;
        }
      }
      v15 = *(struct _UNICODE_STRING **)(a2 + 168);
      String2 = 0;
      FindFileExtension((struct _FILE_ID_EXTD_DIR_INFORMATION *)a1, &String2);
      if ( String2.Length <= 0x14u )
      {
        for ( i = (PCUNICODE_STRING *)&off_18002F8D0; i != (PCUNICODE_STRING *)&qword_18002F8E8; ++i )
        {
          if ( RtlEqualUnicodeString(*i, &String2, 1u) )
            goto LABEL_41;
        }
        v34 = 17;
        v17 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](v5, &v34);
        ++*v17;
        v18 = *(unsigned __int16 **)(a2 + 168);
        Length = String2.Length;
        v20 = v18[1];
        v21 = String2.Length + 6;
        if ( v21 > v20 )
          goto LABEL_43;
        if ( v21 + *v18 > v20 )
        {
          LogAndClearSyncRootNotCloudFileExtensions(*(const unsigned __int16 **)(a2 + 16), v15);
          Length = String2.Length;
        }
        memset(v37, 0, sizeof(v37));
        *(_OWORD *)v36 = 0;
        v22 = StringCchCopyNW(v36, 0x15u, String2.Buffer, (unsigned __int64)Length >> 1);
        if ( v22 >= 0 )
        {
          v22 = CopyBuffer(v15, v36, v23, 0x14u);
          if ( v22 >= 0 )
          {
LABEL_43:
            if ( (*(_DWORD *)(a1 + 68) & 0x4000) != 0 )
            {
              v34 = 22;
              v27 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](v5, &v34);
              ++*v27;
            }
            v28 = *(_DWORD *)(a1 + 56) & 0x100000;
            if ( (*(_DWORD *)(a1 + 56) & 0x80000) != 0 )
            {
              if ( v28 )
                v34 = 10;
              else
                v34 = 7;
            }
            else
            {
              v34 = 8;
              if ( !v28 )
                v34 = 9;
            }
            v29 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](v5, &v34);
            ++*v29;
            if ( (*(_BYTE *)(a1 + 56) & 1) != 0 )
            {
              v34 = 41;
              v30 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](v5, &v34);
              ++*v30;
            }
            v31 = *(_QWORD *)(a1 + 48);
            if ( v31 )
            {
              v34 = 4;
              if ( v31 >= *(_QWORD *)(a1 + 40) )
                v34 = 2;
            }
            else
            {
              v34 = 3;
            }
            v32 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](v5, &v34);
            ++*v32;
            if ( (*(_DWORD *)(a1 + 56) & 0x200) != 0 )
            {
              v34 = 42;
              v33 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](v5, &v34);
              ++*v33;
            }
            UpdateLastAccessTimesMap(a1, 0, *(_QWORD *)(a2 + 160));
            UpdateFileCountsMap(a1, *(_QWORD *)(a2 + 152));
            return 0;
          }
          v24 = 851;
        }
        else
        {
          v24 = 845;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
          (const char *)(unsigned int)v22,
          v34);
        return (unsigned int)v22;
      }
LABEL_41:
      v34 = 21;
LABEL_42:
      v26 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](v5, &v34);
      ++*v26;
      goto LABEL_43;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001d8b0  mov     [rsp-38h+arg_10], rbx
0x18001d8b5  push    rbp
0x18001d8b6  push    rsi
0x18001d8b7  push    rdi
0x18001d8b8  push    r12
0x18001d8ba  push    r13
0x18001d8bc  push    r14
0x18001d8be  push    r15
0x18001d8c0  mov     rbp, rsp
0x18001d8c3  sub     rsp, 70h
0x18001d8c7  mov     rax, cs:__security_cookie
0x18001d8ce  xor     rax, rsp
0x18001d8d1  mov     [rbp+var_8], rax
0x18001d8d5  lea     eax, [r8-8]
0x18001d8d9  mov     r15, rdx
0x18001d8dc  mov     rdi, rcx
0x18001d8df  test    eax, 0FFFFFFF7h
0x18001d8e4  jz      loc_18001DC76
0x18001d8ea  mov     rbx, [rdx+98h]
0x18001d8f1  mov     r13d, 1
0x18001d8f7  cmp     r8d, r13d
0x18001d8fa  jnz     loc_18001DA0E
0x18001d900  mov     edx, [rcx+44h]
0x18001d903  mov     ecx, 9000001Ah
0x18001d908  mov     eax, edx
0x18001d90a  and     eax, ecx
0x18001d90c  cmp     eax, ecx
0x18001d90e  jnz     short loc_18001D956
0x18001d910  mov     r8d, [rdi+38h]
0x18001d914  and     edx, 6FFF0FE5h
0x18001d91a  setz    cl
0x18001d91d  bt      r8d, 0Ah
0x18001d922  setb    al
0x18001d925  test    al, cl
0x18001d927  jz      short loc_18001D932
0x18001d929  mov     [rbp+var_50], 10h
0x18001d930  jmp     short loc_18001D95D
0x18001d932  test    edx, edx
0x18001d934  setnz   cl
0x18001d937  bt      r8d, 0Ah
0x18001d93c  setb    al
0x18001d93f  test    al, cl
0x18001d941  jz      short loc_18001D94F
0x18001d943  mov     r14d, 14h
0x18001d949  mov     [rbp+var_50], r14d
0x18001d94d  jmp     short loc_18001D95D
0x18001d94f  bt      r8d, 0Ah
0x18001d954  jb      short loc_18001D96C
0x18001d956  mov     [rbp+var_50], 12h
0x18001d95d  lea     rdx, [rbp+var_50]
0x18001d961  mov     rcx, rbx
0x18001d964  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d969  add     [rax], r13
0x18001d96c  test    dword ptr [rdi+44h], 4000h
0x18001d973  jz      short loc_18001D98B
0x18001d975  lea     rdx, [rbp+var_50]
0x18001d979  mov     [rbp+var_50], 16h
0x18001d980  mov     rcx, rbx
0x18001d983  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d988  add     [rax], r13
0x18001d98b  lea     rdx, [rbp+var_50]
0x18001d98f  mov     [rbp+var_50], 0
0x18001d996  mov     rcx, rbx
0x18001d999  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d99e  lea     rdx, [rbp+var_50]
0x18001d9a2  mov     rcx, rbx
0x18001d9a5  add     [rax], r13
0x18001d9a8  mov     eax, [rdi+38h]
0x18001d9ab  and     eax, 100000h
0x18001d9b0  test    dword ptr [rdi+38h], 80000h
0x18001d9b7  jz      short loc_18001D9CF
0x18001d9b9  test    eax, eax
0x18001d9bb  jz      short loc_18001D9C6
0x18001d9bd  mov     [rbp+var_50], 0Eh
0x18001d9c4  jmp     short loc_18001D9E1
0x18001d9c6  mov     [rbp+var_50], 0Bh
0x18001d9cd  jmp     short loc_18001D9E1
0x18001d9cf  mov     [rbp+var_50], 0Ch
0x18001d9d6  test    eax, eax
0x18001d9d8  jnz     short loc_18001D9E1
0x18001d9da  mov     [rbp+var_50], 0Dh
0x18001d9e1  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d9e6  add     [rax], r13
0x18001d9e9  test    [rdi+38h], r13b
0x18001d9ed  jz      loc_18001DC76
0x18001d9f3  lea     rdx, [rbp+var_50]
0x18001d9f7  mov     [rbp+var_50], 29h ; ')'
0x18001d9fe  mov     rcx, rbx
0x18001da01  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001da06  add     [rax], r13
0x18001da09  jmp     loc_18001DC76
0x18001da0e  cmp     r8d, 4
0x18001da12  jnz     loc_18001DC76
0x18001da18  mov     eax, [rcx+44h]
0x18001da1b  mov     ecx, 9000001Ah
0x18001da20  and     eax, ecx
0x18001da22  cmp     eax, ecx
0x18001da24  jnz     short loc_18001DA56
0x18001da26  test    dword ptr [rdi+44h], 6FFF0FE5h
0x18001da2d  mov     eax, 400h
0x18001da32  jnz     short loc_18001DA45
0x18001da34  test    [rdi+38h], eax
0x18001da37  jz      short loc_18001DA56
0x18001da39  mov     [rbp+var_50], 0Fh
0x18001da40  jmp     loc_18001DB70
0x18001da45  test    [rdi+38h], eax
0x18001da48  jz      short loc_18001DA56
0x18001da4a  mov     [rbp+var_50], 13h
0x18001da51  jmp     loc_18001DB70
0x18001da56  mov     r12, [rdx+0A8h]
0x18001da5d  xorps   xmm0, xmm0
0x18001da60  lea     rdx, [rbp+String2]; struct _UNICODE_STRING *
0x18001da64  mov     rcx, rdi; struct _FILE_ID_EXTD_DIR_INFORMATION *
0x18001da67  movups  xmmword ptr [rbp+String2.Length], xmm0
0x18001da6b  call    ?FindFileExtension@@YAJPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAU_UNICODE_STRING@@@Z; FindFileExtension(_FILE_ID_EXTD_DIR_INFORMATION *,_UNICODE_STRING *)
0x18001da70  mov     r14d, 14h
0x18001da76  cmp     [rbp+String2.Length], r14w
0x18001da7b  ja      loc_18001DB69
0x18001da81  lea     rsi, off_18002F8D0
0x18001da88  lea     rax, qword_18002F8E8
0x18001da8f  cmp     rsi, rax
0x18001da92  jz      short loc_18001DAB2
0x18001da94  mov     rcx, [rsi]; String1
0x18001da97  lea     rdx, [rbp+String2]; String2
0x18001da9b  mov     r8b, r13b; CaseInsensitive
0x18001da9e  call    cs:__imp_RtlEqualUnicodeString
0x18001daa4  test    al, al
0x18001daa6  jnz     loc_18001DB69
0x18001daac  add     rsi, 8
0x18001dab0  jmp     short loc_18001DA88
0x18001dab2  lea     rdx, [rbp+var_50]
0x18001dab6  mov     [rbp+var_50], 11h
0x18001dabd  mov     rcx, rbx
0x18001dac0  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001dac5  add     [rax], r13
0x18001dac8  mov     rdx, [r15+0A8h]
0x18001dacf  movzx   ecx, [rbp+String2.Length]
0x18001dad3  movzx   r8d, word ptr [rdx+2]
0x18001dad8  lea     r9d, [rcx+6]
0x18001dadc  cmp     r9d, r8d
0x18001dadf  ja      loc_18001DB7F
0x18001dae5  movzx   eax, word ptr [rdx]
0x18001dae8  add     eax, r9d
0x18001daeb  cmp     eax, r8d
0x18001daee  jbe     short loc_18001DB00
0x18001daf0  mov     rcx, [r15+10h]; unsigned __int16 *
0x18001daf4  mov     rdx, r12; struct _UNICODE_STRING *
0x18001daf7  call    ?LogAndClearSyncRootNotCloudFileExtensions@@YAXPEBGPEAU_UNICODE_STRING@@@Z; LogAndClearSyncRootNotCloudFileExtensions(ushort const *,_UNICODE_STRING *)
0x18001dafc  movzx   ecx, [rbp+String2.Length]
0x18001db00  mov     r8, [rbp+String2.Buffer]; unsigned __int16 *
0x18001db04  xorps   xmm0, xmm0
0x18001db07  movzx   r9d, cx
0x18001db0b  mov     edx, 15h; unsigned __int64
0x18001db10  movups  xmmword ptr [rbp+var_28], xmm0
0x18001db14  shr     r9, 1; unsigned __int64
0x18001db17  lea     rcx, [rbp+var_38]; unsigned __int16 *
0x18001db1b  movups  xmmword ptr [rbp+var_28+0Ah], xmm0
0x18001db1f  movups  xmmword ptr [rbp+var_38], xmm0
0x18001db23  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001db28  mov     esi, eax
0x18001db2a  test    eax, eax
0x18001db2c  jns     short loc_18001DB4D
0x18001db2e  mov     edx, 34Dh; void *
0x18001db33  mov     rcx, [rbp+38h]; this
0x18001db37  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18001db3e  mov     r9d, esi; char *
0x18001db41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db46  mov     eax, esi
0x18001db48  jmp     loc_18001DC78
0x18001db4d  mov     r9d, r14d; unsigned int
0x18001db50  lea     rdx, [rbp+var_38]; unsigned __int16 *
0x18001db54  mov     rcx, r12; struct _UNICODE_STRING *
0x18001db57  call    ?CopyBuffer@@YAJPEAU_UNICODE_STRING@@PEBGGK@Z; CopyBuffer(_UNICODE_STRING *,ushort const *,ushort,ulong)
0x18001db5c  mov     esi, eax
0x18001db5e  test    eax, eax
0x18001db60  jns     short loc_18001DB7F
0x18001db62  mov     edx, 353h
0x18001db67  jmp     short loc_18001DB33
0x18001db69  mov     [rbp+var_50], 15h
0x18001db70  lea     rdx, [rbp+var_50]
0x18001db74  mov     rcx, rbx
0x18001db77  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001db7c  add     [rax], r13
0x18001db7f  test    dword ptr [rdi+44h], 4000h
0x18001db86  jz      short loc_18001DB9E
0x18001db88  lea     rdx, [rbp+var_50]
0x18001db8c  mov     [rbp+var_50], 16h
0x18001db93  mov     rcx, rbx
0x18001db96  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001db9b  add     [rax], r13
0x18001db9e  mov     eax, [rdi+38h]
0x18001dba1  lea     rdx, [rbp+var_50]
0x18001dba5  and     eax, 100000h
0x18001dbaa  mov     rcx, rbx
0x18001dbad  test    dword ptr [rdi+38h], 80000h
0x18001dbb4  jz      short loc_18001DBCC
0x18001dbb6  test    eax, eax
0x18001dbb8  jz      short loc_18001DBC3
0x18001dbba  mov     [rbp+var_50], 0Ah
0x18001dbc1  jmp     short loc_18001DBDE
0x18001dbc3  mov     [rbp+var_50], 7
0x18001dbca  jmp     short loc_18001DBDE
0x18001dbcc  mov     [rbp+var_50], 8
0x18001dbd3  test    eax, eax
0x18001dbd5  jnz     short loc_18001DBDE
0x18001dbd7  mov     [rbp+var_50], 9
0x18001dbde  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001dbe3  add     [rax], r13
0x18001dbe6  test    [rdi+38h], r13b
0x18001dbea  jz      short loc_18001DC02
0x18001dbec  lea     rdx, [rbp+var_50]
0x18001dbf0  mov     [rbp+var_50], 29h ; ')'
0x18001dbf7  mov     rcx, rbx
0x18001dbfa  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001dbff  add     [rax], r13
0x18001dc02  mov     rax, [rdi+30h]
0x18001dc06  test    rax, rax
0x18001dc09  jnz     short loc_18001DC14
0x18001dc0b  mov     [rbp+var_50], 3
0x18001dc12  jmp     short loc_18001DC28
0x18001dc14  mov     [rbp+var_50], 4
0x18001dc1b  cmp     rax, [rdi+28h]
0x18001dc1f  jl      short loc_18001DC28
0x18001dc21  mov     [rbp+var_50], 2
0x18001dc28  lea     rdx, [rbp+var_50]
0x18001dc2c  mov     rcx, rbx
0x18001dc2f  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001dc34  add     [rax], r13
0x18001dc37  test    dword ptr [rdi+38h], 200h
0x18001dc3e  jz      short loc_18001DC56
0x18001dc40  lea     rdx, [rbp+var_50]
0x18001dc44  mov     [rbp+var_50], 2Ah ; '*'
0x18001dc4b  mov     rcx, rbx
0x18001dc4e  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001dc53  add     [rax], r13
0x18001dc56  mov     r8, [r15+0A0h]
0x18001dc5d  xor     edx, edx
0x18001dc5f  mov     rcx, rdi
0x18001dc62  call    ?UpdateLastAccessTimesMap@@YAXPEAU_FILE_ID_EXTD_DIR_INFORMATION@@EPEAV?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@@Z; UpdateLastAccessTimesMap(_FILE_ID_EXTD_DIR_INFORMATION *,uchar,std::map<ulong,unsigned __int64> *)
0x18001dc67  mov     rdx, [r15+98h]
0x18001dc6e  mov     rcx, rdi
0x18001dc71  call    ?UpdateFileCountsMap@@YAXPEAU_FILE_ID_EXTD_DIR_INFORMATION@@PEAV?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@@Z; UpdateFileCountsMap(_FILE_ID_EXTD_DIR_INFORMATION *,std::map<ulong,unsigned __int64> *)
0x18001dc76  xor     eax, eax
0x18001dc78  mov     rcx, [rbp+var_8]
0x18001dc7c  xor     rcx, rsp; StackCookie
0x18001dc7f  call    __security_check_cookie
0x18001dc84  mov     rbx, [rsp+70h+arg_10]
0x18001dc8c  add     rsp, 70h
0x18001dc90  pop     r15
0x18001dc92  pop     r14
0x18001dc94  pop     r13
0x18001dc96  pop     r12
0x18001dc98  pop     rdi
0x18001dc99  pop     rsi
0x18001dc9a  pop     rbp
0x18001dc9b  retn
```
