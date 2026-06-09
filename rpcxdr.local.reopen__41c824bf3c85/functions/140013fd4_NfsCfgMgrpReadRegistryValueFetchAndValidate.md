# NfsCfgMgrpReadRegistryValueFetchAndValidate

- ea: `0x140013fd4`
- end: `0x14001480b`
- name: `NfsCfgMgrpReadRegistryValueFetchAndValidate`
- size: `2103`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140013b78`
- `0x140013de4`

## callees

- `0x1400107d0`
- `0x140013fd4`
- `0x140015640`
- `0x140015680`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400140db`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400143ab`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140014729`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400140db`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400143ab`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140014729`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140014121`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400143cc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140014121`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400143cc`
- `ntoskrnl!ZwClose` at `0x140014225`
- `ntoskrnl!ZwClose` at `0x140014225`
- `ntoskrnl!ZwQueryValueKey` at `0x1400141b4`
- `ntoskrnl!ZwQueryValueKey` at `0x1400143ff`
- `ntoskrnl!ZwQueryValueKey` at `0x1400141b4`
- `ntoskrnl!ZwQueryValueKey` at `0x1400143ff`
- `ntoskrnl!ZwOpenKey` at `0x14001415d`
- `ntoskrnl!ZwOpenKey` at `0x14001415d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400147c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400147c0`
- `ntoskrnl!ExAllocatePool2` at `0x140014786`
- `ntoskrnl!ExAllocatePool2` at `0x140014786`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400146b0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400146b0`

## pseudocode

```c
__int64 __fastcall NfsCfgMgrpReadRegistryValueFetchAndValidate(__int64 a1, void *a2, ULONG a3, unsigned __int16 *a4)
{
  unsigned int v5; // edx
  __int64 v6; // rbx
  unsigned __int16 v8; // r14
  unsigned int v9; // edi
  __int64 (__fastcall *v10)(__int64, _QWORD, _QWORD, __int64, UNICODE_STRING *); // r12
  __int64 (__fastcall *v11)(__int64, _QWORD, _QWORD, __int64, __int128 *, UNICODE_STRING *); // r13
  __int64 v12; // rax
  __int128 v13; // xmm0
  unsigned int v14; // r15d
  unsigned int v15; // eax
  int v16; // r13d
  __int64 v17; // r14
  ULONG Length; // ebx
  NTSTATUS v19; // eax
  __int64 v20; // rax
  unsigned int v21; // r14d
  unsigned int v22; // esi
  unsigned int v23; // r8d
  int Buffer_high; // r9d
  unsigned int v25; // ecx
  unsigned int Buffer; // edx
  int v27; // r10d
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // edx
  unsigned int v32; // ecx
  int v33; // eax
  __int64 v34; // r8
  bool v35; // cf
  unsigned __int64 *v36; // rdx
  int v37; // edx
  unsigned __int64 v38; // rcx
  unsigned __int16 v39; // ax
  unsigned __int16 v40; // r14
  unsigned __int16 v41; // ax
  __int64 v42; // r14
  int v43; // esi
  int v44; // r8d
  int v45; // r8d
  int v46; // r8d
  unsigned __int64 v47; // rax
  __int64 v48; // r10
  unsigned __int64 v49; // r9
  int v50; // r8d
  int v51; // eax
  unsigned __int64 v52; // r10
  unsigned int v53; // eax
  int v54; // r8d
  int v55; // r8d
  int v56; // r8d
  int v57; // r8d
  int v58; // r8d
  bool v59; // al
  bool v60; // zf
  bool v61; // zf
  struct _UNICODE_STRING v62; // xmm0
  __int64 v64; // [rsp+40h] [rbp-C0h]
  int v65; // [rsp+48h] [rbp-B8h]
  ULONG ResultLength; // [rsp+4Ch] [rbp-B4h] BYREF
  ULONG v67; // [rsp+50h] [rbp-B0h]
  unsigned int v68; // [rsp+54h] [rbp-ACh]
  unsigned int v69; // [rsp+58h] [rbp-A8h]
  void *KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  _BYTE LockHandle[32]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v73; // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v74)(__int64, _QWORD, _QWORD, __int64, UNICODE_STRING *); // [rsp+A0h] [rbp-60h]
  __int64 (__fastcall *v75)(__int64, _QWORD, _QWORD, __int64, __int128 *, UNICODE_STRING *); // [rsp+A8h] [rbp-58h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING String2; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v78; // [rsp+F0h] [rbp-10h] BYREF
  PUNICODE_STRING ValueName; // [rsp+100h] [rbp+0h]
  __int128 v80; // [rsp+108h] [rbp+8h]
  __int64 *v81; // [rsp+118h] [rbp+18h]
  __int128 v82; // [rsp+120h] [rbp+20h]
  __int64 *v83; // [rsp+130h] [rbp+30h]
  __int128 v84; // [rsp+138h] [rbp+38h]
  __int64 *v85; // [rsp+148h] [rbp+48h]
  __int128 v86; // [rsp+150h] [rbp+50h]

  v73 = a1;
  v67 = a3;
  KeyHandle = 0;
  v5 = *(_DWORD *)(a1 + 60);
  ResultLength = 0;
  v6 = a1;
  v8 = a3;
  memset(LockHandle, 0, sizeof(LockHandle));
  memset(&ObjectAttributes, 0, 44);
  String2 = 0;
  DestinationString = 0;
  v78 = 0;
  if ( v5 >= 6 && v5 != 7 )
    return (unsigned int)-1073741811;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, UNICODE_STRING *))(a1 + 112);
  v11 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int128 *, UNICODE_STRING *))(a1 + 120);
  v12 = *(_QWORD *)(a1 + 104);
  v74 = v10;
  v75 = v11;
  v64 = v12;
  if ( v5 == 7 )
  {
    ValueName = (PUNICODE_STRING)&qword_14001A110;
    v81 = &qword_14001A100;
    v83 = &qword_14001A0F0;
    v85 = &qword_14001A0E0;
    v80 = 0;
    v82 = 0;
    v84 = 0;
    v86 = 0;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 24), (PKLOCK_QUEUE_HANDLE)LockHandle);
    v13 = *(_OWORD *)(v6 + 232);
    v14 = *(_DWORD *)(v6 + 240);
    v69 = *(_DWORD *)(v6 + 236);
    LODWORD(v82) = v69;
    v15 = *(_DWORD *)(v6 + 244);
    v78 = v13;
    LODWORD(v84) = v14;
    v68 = v15;
    LODWORD(v80) = v15;
    LockHandle[24] = 0;
    KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)LockHandle);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)(v6 + 64);
    ObjectAttributes.RootDirectory = a2;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v16 = 0;
    v17 = 0;
    v65 = 0;
    v9 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( (v9 & 0x80000000) == 0 )
    {
      Length = v67;
      while ( 1 )
      {
        if ( (unsigned int)v17 >= 4 )
        {
LABEL_16:
          v14 = v84;
          v21 = v82;
          v22 = v80;
          v6 = v73;
          v16 = v65;
          goto LABEL_18;
        }
        v19 = ZwQueryValueKey(KeyHandle, *(&ValueName + 3 * v17), KeyValueFullInformation, a4, Length, &ResultLength);
        v9 = v19;
        if ( v19 == -1073741772 )
          break;
        if ( v19 >= 0 && *((_DWORD *)a4 + 1) == 4 && *((_DWORD *)a4 + 3) == 4 )
        {
          v20 = *((unsigned int *)a4 + 2);
          ++v65;
          *((_BYTE *)&v80 + 24 * v17 + 8) = 1;
          *((_DWORD *)&v80 + 6 * v17 + 1) = *(_DWORD *)((char *)a4 + v20);
LABEL_10:
          v17 = (unsigned int)(v17 + 1);
        }
        else
        {
          v17 = (unsigned int)(v17 + 1);
          if ( v19 < 0 )
            goto LABEL_16;
        }
      }
      v9 = 0;
      goto LABEL_10;
    }
    v22 = v68;
    v21 = v69;
LABEL_18:
    if ( KeyHandle )
      ZwClose(KeyHandle);
    if ( v9 == -1073741772 )
      return 0;
    if ( (v9 & 0x80000000) == 0 && v16 )
    {
      v23 = v22;
      Buffer_high = v86;
      v25 = v21;
      if ( BYTE8(v80) )
        v23 = DWORD1(v80);
      Buffer = v14;
      if ( BYTE8(v82) )
        v25 = DWORD1(v82);
      if ( BYTE8(v84) )
        Buffer = DWORD1(v84);
      *(_DWORD *)&String2.Length = v23;
      if ( BYTE8(v86) )
        Buffer_high = DWORD1(v86);
      *(_DWORD *)(&String2.MaximumLength + 1) = v25;
      String2.Buffer = (wchar_t *)__PAIR64__(Buffer_high, Buffer);
      if ( v74 )
      {
        v27 = v74(v64, *(unsigned int *)(v6 + 40), *(unsigned int *)(v6 + 60), v6 + 80, &String2);
        if ( v27 < 0 )
          return v9;
        Buffer_high = HIDWORD(String2.Buffer);
        Buffer = (unsigned int)String2.Buffer;
        v25 = *(_DWORD *)(&String2.MaximumLength + 1);
        v23 = *(_DWORD *)&String2.Length;
      }
      else
      {
        v27 = 0;
      }
      if ( Buffer_high == -1 )
      {
        Buffer_high = -1;
        HIDWORD(String2.Buffer) = -1;
      }
      else
      {
        if ( !Buffer_high )
          Buffer_high = 0;
        HIDWORD(String2.Buffer) = Buffer_high;
      }
      v28 = 0;
      if ( Buffer )
        v28 = Buffer;
      if ( v28 >= v25 )
      {
        Buffer = v25;
        LODWORD(String2.Buffer) = v25;
      }
      else if ( !Buffer )
      {
        LODWORD(String2.Buffer) = 0;
      }
      v29 = Buffer;
      if ( v25 > Buffer )
        v29 = v25;
      if ( v29 >= v23 )
      {
        v25 = v23;
        *(_DWORD *)(&String2.MaximumLength + 1) = v23;
      }
      else if ( v25 <= Buffer )
      {
        v25 = Buffer;
        *(_DWORD *)(&String2.MaximumLength + 1) = Buffer;
      }
      v30 = v25;
      if ( v23 > v25 )
        v30 = v23;
      if ( v30 == -1 )
      {
        v23 = -1;
        *(_DWORD *)&String2.Length = -1;
      }
      else if ( v23 <= v25 )
      {
        v23 = v25;
        *(_DWORD *)&String2.Length = v25;
      }
      if ( v23 != v22 || v25 != v21 || Buffer != v14 || Buffer_high != (_DWORD)v86 )
      {
        if ( v75 )
          v27 = v75(v64, *(unsigned int *)(v6 + 40), *(unsigned int *)(v6 + 60), v6 + 80, &v78, &String2);
        if ( v27 >= 0 )
        {
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 24), (PKLOCK_QUEUE_HANDLE)LockHandle);
          *(UNICODE_STRING *)(v6 + 232) = String2;
          goto LABEL_67;
        }
      }
    }
    return v9;
  }
  v9 = ZwQueryValueKey(a2, (PUNICODE_STRING)(a1 + 256), KeyValueFullInformation, a4, a3, &ResultLength);
  if ( (v9 & 0x80000000) != 0 )
  {
    if ( v9 == -1073741772 )
      return 0;
    return v9;
  }
  v31 = *((_DWORD *)a4 + 2);
  if ( *((_DWORD *)a4 + 4) + 20 > v31 )
    return (unsigned int)-1073741811;
  v32 = *((_DWORD *)a4 + 3);
  if ( v31 + v32 > ResultLength )
    return (unsigned int)-1073741811;
  v33 = *((_DWORD *)a4 + 1);
  if ( v33 == 4 )
  {
    if ( v32 != 4 )
      return (unsigned int)-1073741811;
  }
  else if ( (v33 != 11 || v32 != 8) && (v33 != 1 || v32 > 0xFFFF) )
  {
    return (unsigned int)-1073741811;
  }
  v34 = *(unsigned int *)(v6 + 60);
  v9 = 0;
  switch ( (_DWORD)v34 )
  {
    case 0:
      goto LABEL_88;
    case 1:
      goto LABEL_85;
    case 2:
LABEL_88:
      if ( v33 == 4 )
        goto LABEL_89;
      return (unsigned int)-1073741811;
  }
  if ( (_DWORD)v34 != 3 )
  {
    if ( (_DWORD)v34 != 4 )
    {
      if ( (_DWORD)v34 != 5 )
        goto LABEL_89;
      v35 = *((_DWORD *)a4 + 1) != 1;
      goto LABEL_86;
    }
    goto LABEL_88;
  }
LABEL_85:
  v35 = v33 != 11;
LABEL_86:
  v9 = v35 ? 0xC000000D : 0;
  if ( v35 )
    return v9;
LABEL_89:
  v36 = (unsigned __int64 *)((char *)a4 + *((unsigned int *)a4 + 2));
  if ( (_DWORD)v34 )
  {
    switch ( (_DWORD)v34 )
    {
      case 1:
        goto LABEL_99;
      case 2:
        goto LABEL_100;
      case 3:
LABEL_99:
        v38 = *v36;
        v37 = *v36;
        *(_QWORD *)&String2.Length = v38;
        goto LABEL_102;
    }
    if ( (_DWORD)v34 != 4 )
    {
      if ( (_DWORD)v34 != 5 )
      {
        String2 = 0;
        v37 = _mm_cvtsi128_si32((__m128i)0LL);
        v38 = 0;
        goto LABEL_102;
      }
      v39 = a4[4];
      if ( v8 < v39 )
        return (unsigned int)-1073741675;
      v40 = v8 - v39;
      LODWORD(String2.Buffer) = (_DWORD)a4 + *((_DWORD *)a4 + 2);
      v41 = a4[6];
      v9 = 0;
      HIDWORD(String2.Buffer) = HIDWORD(v36);
      String2.MaximumLength = v40;
      String2.Length = v41;
      v37 = *(_DWORD *)&String2.Length;
      goto LABEL_101;
    }
  }
LABEL_100:
  v37 = *(_DWORD *)v36;
  *(_DWORD *)&String2.Length = v37;
LABEL_101:
  v38 = *(_QWORD *)&String2.Length;
LABEL_102:
  if ( v10 )
  {
    v42 = v64;
    v43 = v10(v64, *(unsigned int *)(v6 + 40), v34, v6 + 80, &String2);
    if ( v43 < 0 )
      return v9;
    v37 = *(_DWORD *)&String2.Length;
    goto LABEL_136;
  }
  v43 = 0;
  if ( (_DWORD)v34 )
  {
    v44 = v34 - 1;
    if ( !v44 )
    {
      v47 = *(_QWORD *)(v6 + 96);
      v52 = v38;
      if ( v38 <= v47 )
        v52 = *(_QWORD *)(v6 + 96);
      v49 = *(_QWORD *)(v6 + 88);
      if ( v52 < v49 )
      {
        v42 = v64;
        if ( v38 > v47 )
          goto LABEL_137;
LABEL_115:
        v38 = v47;
        *(_QWORD *)&String2.Length = v47;
        v37 = v47;
        goto LABEL_137;
      }
      goto LABEL_116;
    }
    v45 = v44 - 1;
    if ( v45 )
    {
      v46 = v45 - 1;
      if ( v46 )
      {
        v42 = v64;
        if ( v46 != 1 )
          goto LABEL_137;
        v37 &= *(_DWORD *)(v6 + 84);
        goto LABEL_135;
      }
      v47 = *(_QWORD *)(v6 + 96);
      v48 = v38;
      if ( (__int64)v38 <= (__int64)v47 )
        v48 = *(_QWORD *)(v6 + 96);
      v49 = *(_QWORD *)(v6 + 88);
      if ( v48 < (__int64)v49 )
      {
        v42 = v64;
        if ( (__int64)v38 > (__int64)v47 )
          goto LABEL_137;
        goto LABEL_115;
      }
LABEL_116:
      v38 = v49;
      v37 = v49;
      *(_QWORD *)&String2.Length = v49;
LABEL_117:
      v42 = v64;
      goto LABEL_137;
    }
    v50 = *(_DWORD *)(v6 + 88);
    v51 = v50;
    if ( v37 > v50 )
      v51 = v37;
    if ( v51 >= *(_DWORD *)(v6 + 84) )
    {
      v37 = *(_DWORD *)(v6 + 84);
      *(_DWORD *)&String2.Length = v37;
      v38 = *(_QWORD *)&String2.Length;
      goto LABEL_117;
    }
    v42 = v64;
    if ( v37 > v50 )
      goto LABEL_137;
  }
  else
  {
    v50 = *(_DWORD *)(v6 + 88);
    v53 = v50;
    v42 = v64;
    if ( v37 > (unsigned int)v50 )
      v53 = v37;
    if ( v53 >= *(_DWORD *)(v6 + 84) )
    {
      v37 = *(_DWORD *)(v6 + 84);
      goto LABEL_135;
    }
    if ( v37 > (unsigned int)v50 )
      goto LABEL_137;
  }
  v37 = v50;
LABEL_135:
  *(_DWORD *)&String2.Length = v37;
LABEL_136:
  v38 = *(_QWORD *)&String2.Length;
LABEL_137:
  v54 = *(_DWORD *)(v6 + 60);
  if ( v54 )
  {
    v55 = v54 - 1;
    if ( v55 )
    {
      v56 = v55 - 1;
      if ( !v56 )
      {
LABEL_144:
        v60 = v37 == *(_DWORD *)(v6 + 232);
LABEL_146:
        if ( !v60 )
          goto LABEL_151;
        v59 = 0;
        goto LABEL_148;
      }
      v57 = v56 - 1;
      if ( v57 )
      {
        v58 = v57 - 1;
        if ( v58 )
        {
          if ( v58 != 1 )
            return v9;
          v59 = RtlEqualUnicodeString((PCUNICODE_STRING)(v6 + 232), &String2, *(_BYTE *)(v6 + 96) == 0) == 0;
LABEL_148:
          v61 = !v59;
          goto LABEL_150;
        }
        goto LABEL_144;
      }
    }
    v60 = v38 == *(_QWORD *)(v6 + 232);
    goto LABEL_146;
  }
  v61 = v37 == *(_DWORD *)(v6 + 232);
LABEL_150:
  if ( v61 )
    return v9;
LABEL_151:
  if ( v11 )
    v43 = v11(v42, *(unsigned int *)(v6 + 40), *(unsigned int *)(v6 + 60), v6 + 80, (__int128 *)(v6 + 232), &String2);
  if ( v43 >= 0 )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v6 + 24), (PKLOCK_QUEUE_HANDLE)LockHandle);
    v60 = *(_DWORD *)(v6 + 60) == 5;
    LockHandle[24] = 1;
    if ( v60 )
    {
      if ( RtlUnicodeStringCopy((PUNICODE_STRING)(v6 + 232), &String2) >= 0 )
        goto LABEL_67;
      DestinationString.MaximumLength = String2.Length + 2;
      DestinationString.Length = 0;
      DestinationString.Buffer = (wchar_t *)ExAllocatePool2(66, (unsigned __int16)(String2.Length + 2), 1396855363);
      if ( !DestinationString.Buffer || RtlUnicodeStringCopy(&DestinationString, &String2) < 0 )
        goto LABEL_67;
      ExFreePoolWithTag(*(PVOID *)(v6 + 240), 0x53425243u);
      v62 = DestinationString;
    }
    else
    {
      v62 = String2;
    }
    *(struct _UNICODE_STRING *)(v6 + 232) = v62;
LABEL_67:
    LockHandle[24] = 0;
    KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)LockHandle);
  }
  return v9;
}

```

## disassembly

```asm
0x140013fd4  push    rbp
0x140013fd6  push    rbx
0x140013fd7  push    rsi
0x140013fd8  push    rdi
0x140013fd9  push    r12
0x140013fdb  push    r13
0x140013fdd  push    r14
0x140013fdf  push    r15
0x140013fe1  lea     rbp, [rsp-78h]
0x140013fe6  sub     rsp, 178h
0x140013fed  mov     rax, cs:__security_cookie
0x140013ff4  xor     rax, rsp
0x140013ff7  mov     [rbp+0B0h+var_50], rax
0x140013ffb  xorps   xmm0, xmm0
0x140013ffe  mov     [rbp+0B0h+var_118], rcx
0x140014002  xor     eax, eax
0x140014004  mov     [rsp+1B0h+var_160], r8d
0x140014009  mov     rdi, rdx
0x14001400c  mov     [rsp+1B0h+KeyHandle], rax
0x140014011  mov     edx, [rcx+3Ch]
0x140014014  xorps   xmm1, xmm1
0x140014017  mov     [rsp+1B0h+var_164], eax
0x14001401b  mov     rbx, rcx
0x14001401e  mov     rsi, r9
0x140014021  mov     r14d, r8d
0x140014024  mov     ecx, edx
0x140014026  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.ObjectName], xmm0
0x14001402a  movups  xmmword ptr [rbp+0B0h+ObjectAttributes+1Ch], xmm0
0x14001402e  movups  xmmword ptr [rsp+1B0h+LockHandle], xmm0
0x140014033  movups  xmmword ptr [rbp+0B0h+LockHandle+10h], xmm0
0x140014037  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.Length], xmm0
0x14001403b  movups  xmmword ptr [rbp+0B0h+String2.Length], xmm0
0x14001403f  movups  xmmword ptr [rsp+1B0h+DestinationString.Length], xmm1
0x140014044  movups  [rbp+0B0h+var_C0], xmm0
0x140014048  test    edx, edx
0x14001404a  jz      short loc_140014074
0x14001404c  sub     ecx, 1
0x14001404f  jz      short loc_140014074
0x140014051  sub     ecx, 1
0x140014054  jz      short loc_140014074
0x140014056  sub     ecx, 1
0x140014059  jz      short loc_140014074
0x14001405b  sub     ecx, 1
0x14001405e  jz      short loc_140014074
0x140014060  sub     ecx, 1
0x140014063  jz      short loc_140014074
0x140014065  cmp     ecx, 2
0x140014068  jz      short loc_140014074
0x14001406a  mov     edi, 0C000000Dh
0x14001406f  jmp     loc_1400147E8
0x140014074  mov     r12, [rbx+70h]
0x140014078  mov     r13, [rbx+78h]
0x14001407c  mov     rax, [rbx+68h]
0x140014080  mov     [rbp+0B0h+var_110], r12
0x140014084  mov     [rbp+0B0h+var_108], r13
0x140014088  mov     [rsp+1B0h+var_170], rax
0x14001408d  cmp     edx, 7
0x140014090  jnz     loc_1400143DD
0x140014096  lea     rax, qword_14001A110
0x14001409d  mov     [rbp+0B0h+ValueName], rax
0x1400140a1  lea     rcx, [rbx+18h]; SpinLock
0x1400140a5  lea     rax, qword_14001A100
0x1400140ac  mov     [rbp+0B0h+var_98], rax
0x1400140b0  lea     rdx, [rsp+1B0h+LockHandle]; LockHandle
0x1400140b5  lea     rax, qword_14001A0F0
0x1400140bc  mov     [rbp+0B0h+var_80], rax
0x1400140c0  lea     rax, qword_14001A0E0
0x1400140c7  mov     [rbp+0B0h+var_68], rax
0x1400140cb  movups  [rbp+0B0h+var_A8], xmm0
0x1400140cf  movups  [rbp+0B0h+var_90], xmm0
0x1400140d3  movups  [rbp+0B0h+var_78], xmm0
0x1400140d7  movups  [rbp+0B0h+var_60], xmm0
0x1400140db  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400140e2  nop     dword ptr [rax+rax+00h]
0x1400140e7  mov     eax, [rbx+0ECh]
0x1400140ed  lea     rcx, [rsp+1B0h+LockHandle]; LockHandle
0x1400140f2  movups  xmm0, xmmword ptr [rbx+0E8h]
0x1400140f9  mov     r15d, [rbx+0F0h]
0x140014100  mov     [rsp+1B0h+var_158], eax
0x140014104  mov     dword ptr [rbp+0B0h+var_90], eax
0x140014107  mov     eax, [rbx+0F4h]
0x14001410d  movdqu  [rbp+0B0h+var_C0], xmm0
0x140014112  mov     dword ptr [rbp+0B0h+var_78], r15d
0x140014116  mov     [rsp+1B0h+var_15C], eax
0x14001411a  mov     dword ptr [rbp+0B0h+var_A8], eax
0x14001411d  mov     [rbp+0B0h+LockHandle+18h], 0
0x140014121  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140014128  nop     dword ptr [rax+rax+00h]
0x14001412d  lea     rax, [rbx+40h]
0x140014131  mov     [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x140014138  xorps   xmm0, xmm0
0x14001413b  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x14001413f  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x140014143  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], rdi
0x140014147  mov     edx, 20019h; DesiredAccess
0x14001414c  mov     [rbp+0B0h+ObjectAttributes.Attributes], 240h
0x140014153  lea     rcx, [rsp+1B0h+KeyHandle]; KeyHandle
0x140014158  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001415d  call    cs:__imp_ZwOpenKey
0x140014164  nop     dword ptr [rax+rax+00h]
0x140014169  xor     r13d, r13d
0x14001416c  xor     r14d, r14d
0x14001416f  mov     [rsp+1B0h+var_168], r13d
0x140014174  mov     edi, eax
0x140014176  mov     r12d, 0C0000034h
0x14001417c  test    eax, eax
0x14001417e  js      loc_140014212
0x140014184  mov     ebx, [rsp+1B0h+var_160]
0x140014188  lea     r15d, [r14+1]
0x14001418c  cmp     r14d, 4
0x140014190  jnb     short loc_1400141FC
0x140014192  mov     rcx, [rsp+1B0h+KeyHandle]; KeyHandle
0x140014197  lea     rax, [rsp+1B0h+var_164]
0x14001419c  mov     [rsp+1B0h+ResultLength], rax; ResultLength
0x1400141a1  lea     r13, [r14+r14*2]
0x1400141a5  mov     rdx, [rbp+r13*8+0B0h+ValueName]; ValueName
0x1400141aa  mov     r9, rsi; KeyValueInformation
0x1400141ad  mov     r8d, r15d; KeyValueInformationClass
0x1400141b0  mov     [rsp+1B0h+Length], ebx; Length
0x1400141b4  call    cs:__imp_ZwQueryValueKey
0x1400141bb  nop     dword ptr [rax+rax+00h]
0x1400141c0  mov     edi, eax
0x1400141c2  cmp     eax, r12d
0x1400141c5  jnz     short loc_1400141CE
0x1400141c7  xor     edi, edi
0x1400141c9  add     r14d, r15d
0x1400141cc  jmp     short loc_14001418C
0x1400141ce  test    eax, eax
0x1400141d0  js      short loc_1400141F5
0x1400141d2  cmp     dword ptr [rsi+4], 4
0x1400141d6  jnz     short loc_1400141F5
0x1400141d8  cmp     dword ptr [rsi+0Ch], 4
0x1400141dc  jnz     short loc_1400141F5
0x1400141de  mov     eax, [rsi+8]
0x1400141e1  add     [rsp+1B0h+var_168], r15d
0x1400141e6  mov     byte ptr [rbp+r13*8+0B0h+var_A8+8], r15b
0x1400141eb  mov     ecx, [rax+rsi]
0x1400141ee  mov     dword ptr [rbp+r13*8+0B0h+var_A8+4], ecx
0x1400141f3  jmp     short loc_1400141C9
0x1400141f5  add     r14d, r15d
0x1400141f8  test    eax, eax
0x1400141fa  jns     short loc_14001418C
0x1400141fc  mov     r15d, dword ptr [rbp+0B0h+var_78]
0x140014200  mov     r14d, dword ptr [rbp+0B0h+var_90]
0x140014204  mov     esi, dword ptr [rbp+0B0h+var_A8]
0x140014207  mov     rbx, [rbp+0B0h+var_118]
0x14001420b  mov     r13d, [rsp+1B0h+var_168]
0x140014210  jmp     short loc_14001421B
0x140014212  mov     esi, [rsp+1B0h+var_15C]
0x140014216  mov     r14d, [rsp+1B0h+var_158]
0x14001421b  mov     rcx, [rsp+1B0h+KeyHandle]; Handle
0x140014220  test    rcx, rcx
0x140014223  jz      short loc_140014231
0x140014225  call    cs:__imp_ZwClose
0x14001422c  nop     dword ptr [rax+rax+00h]
0x140014231  cmp     edi, r12d
0x140014234  jnz     short loc_14001423D
0x140014236  xor     edi, edi
0x140014238  jmp     loc_1400147E8
0x14001423d  test    edi, edi
0x14001423f  js      loc_1400147E8
0x140014245  test    r13d, r13d
0x140014248  jz      loc_1400147E8
0x14001424e  cmp     byte ptr [rbp+0B0h+var_A8+8], 0
0x140014252  mov     r8d, esi
0x140014255  mov     r9d, dword ptr [rbp+0B0h+var_60]
0x140014259  mov     ecx, r14d
0x14001425c  cmovnz  r8d, dword ptr [rbp+0B0h+var_A8+4]
0x140014261  mov     edx, r15d
0x140014264  cmp     byte ptr [rbp+0B0h+var_90+8], 0
0x140014268  mov     rax, [rbp+0B0h+var_110]
0x14001426c  cmovnz  ecx, dword ptr [rbp+0B0h+var_90+4]
0x140014270  cmp     byte ptr [rbp+0B0h+var_78+8], 0
0x140014274  mov     r12, [rsp+1B0h+var_170]
0x140014279  cmovnz  edx, dword ptr [rbp+0B0h+var_78+4]
0x14001427d  cmp     byte ptr [rbp+0B0h+var_60+8], 0
0x140014281  mov     dword ptr [rbp+0B0h+String2.Length], r8d
0x140014285  cmovnz  r9d, dword ptr [rbp+0B0h+var_60+4]
0x14001428a  mov     dword ptr [rbp+0B0h+String2.Buffer+4], r9d
0x14001428e  mov     dword ptr [rbp+0B0h+String2+4], ecx
0x140014291  mov     dword ptr [rbp+0B0h+String2.Buffer], edx
0x140014294  test    rax, rax
0x140014297  jnz     short loc_14001429E
0x140014299  xor     r10d, r10d
0x14001429c  jmp     short loc_1400142D3
0x14001429e  mov     r8d, [rbx+3Ch]
0x1400142a2  lea     rcx, [rbp+0B0h+String2]
0x1400142a6  mov     edx, [rbx+28h]
0x1400142a9  lea     r9, [rbx+50h]
0x1400142ad  mov     qword ptr [rsp+1B0h+Length], rcx
0x1400142b2  mov     rcx, r12
0x1400142b5  call    _guard_dispatch_icall
0x1400142ba  mov     r10d, eax
0x1400142bd  test    eax, eax
0x1400142bf  js      loc_1400147E8
0x1400142c5  mov     r9d, dword ptr [rbp+0B0h+String2.Buffer+4]
0x1400142c9  mov     edx, dword ptr [rbp+0B0h+String2.Buffer]
0x1400142cc  mov     ecx, dword ptr [rbp+0B0h+String2+4]
0x1400142cf  mov     r8d, dword ptr [rbp+0B0h+String2.Length]
0x1400142d3  or      r11d, 0FFFFFFFFh
0x1400142d7  test    r9d, r9d
0x1400142da  jz      short loc_1400142EA
0x1400142dc  cmp     r9d, r11d
0x1400142df  jb      short loc_1400142EA
0x1400142e1  mov     r9d, r11d
0x1400142e4  mov     dword ptr [rbp+0B0h+String2.Buffer+4], r11d
0x1400142e8  jmp     short loc_1400142F7
0x1400142ea  xor     eax, eax
0x1400142ec  test    r9d, r9d
0x1400142ef  cmovz   r9d, eax
0x1400142f3  mov     dword ptr [rbp+0B0h+String2.Buffer+4], r9d
0x1400142f7  xor     eax, eax
0x1400142f9  test    edx, edx
0x1400142fb  cmovnz  eax, edx
0x1400142fe  cmp     eax, ecx
0x140014300  jnb     short loc_14001430B
0x140014302  test    edx, edx
0x140014304  jnz     short loc_140014310
0x140014306  mov     dword ptr [rbp+0B0h+String2.Buffer], edx
0x140014309  jmp     short loc_140014310
0x14001430b  mov     edx, ecx
0x14001430d  mov     dword ptr [rbp+0B0h+String2.Buffer], ecx
0x140014310  cmp     ecx, edx
0x140014312  mov     eax, edx
0x140014314  cmova   eax, ecx
0x140014317  cmp     eax, r8d
0x14001431a  jnb     short loc_140014327
0x14001431c  cmp     ecx, edx
0x14001431e  ja      short loc_14001432D
0x140014320  mov     ecx, edx
0x140014322  mov     dword ptr [rbp+0B0h+String2+4], edx
0x140014325  jmp     short loc_14001432D
0x140014327  mov     ecx, r8d
0x14001432a  mov     dword ptr [rbp+0B0h+String2+4], ecx
0x14001432d  cmp     r8d, ecx
0x140014330  mov     eax, ecx
0x140014332  cmova   eax, r8d
0x140014336  cmp     eax, r11d
0x140014339  jnb     short loc_140014348
0x14001433b  cmp     r8d, ecx
0x14001433e  ja      short loc_14001434F
0x140014340  mov     r8d, ecx
0x140014343  mov     dword ptr [rbp+0B0h+String2.Length], ecx
0x140014346  jmp     short loc_14001434F
0x140014348  mov     r8d, r11d
0x14001434b  mov     dword ptr [rbp+0B0h+String2.Length], r11d
0x14001434f  cmp     r8d, esi
0x140014352  jnz     short loc_140014368
0x140014354  cmp     ecx, r14d
0x140014357  jnz     short loc_140014368
0x140014359  cmp     edx, r15d
0x14001435c  jnz     short loc_140014368
0x14001435e  cmp     r9d, dword ptr [rbp+0B0h+var_60]
0x140014362  jz      loc_1400147E8
0x140014368  mov     rax, [rbp+0B0h+var_108]
0x14001436c  test    rax, rax
0x14001436f  jz      short loc_140014399
0x140014371  mov     r8d, [rbx+3Ch]
0x140014375  lea     rcx, [rbp+0B0h+String2]
0x140014379  mov     edx, [rbx+28h]
0x14001437c  lea     r9, [rbx+50h]
0x140014380  mov     [rsp+1B0h+ResultLength], rcx
0x140014385  lea     rcx, [rbp+0B0h+var_C0]
0x140014389  mov     qword ptr [rsp+1B0h+Length], rcx
0x14001438e  mov     rcx, r12
0x140014391  call    _guard_dispatch_icall
0x140014396  mov     r10d, eax
0x140014399  test    r10d, r10d
0x14001439c  js      loc_1400147E8
0x1400143a2  lea     rdx, [rsp+1B0h+LockHandle]; LockHandle
0x1400143a7  lea     rcx, [rbx+18h]; SpinLock
0x1400143ab  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400143b2  nop     dword ptr [rax+rax+00h]
0x1400143b7  movups  xmm0, xmmword ptr [rbp+0B0h+String2.Length]
0x1400143bb  movdqu  xmmword ptr [rbx+0E8h], xmm0
0x1400143c3  lea     rcx, [rsp+1B0h+LockHandle]; LockHandle
0x1400143c8  mov     [rbp+0B0h+LockHandle+18h], 0
0x1400143cc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400143d3  nop     dword ptr [rax+rax+00h]
0x1400143d8  jmp     loc_1400147E8
0x1400143dd  lea     rax, [rsp+1B0h+var_164]
0x1400143e2  mov     r15d, 1
0x1400143e8  mov     [rsp+1B0h+ResultLength], rax; ResultLength
0x1400143ed  lea     rdx, [rbx+100h]; ValueName
0x1400143f4  mov     r8d, r15d; KeyValueInformationClass
0x1400143f7  mov     [rsp+1B0h+Length], r14d; Length
0x1400143fc  mov     rcx, rdi; KeyHandle
0x1400143ff  call    cs:__imp_ZwQueryValueKey
0x140014406  nop     dword ptr [rax+rax+00h]
0x14001440b  mov     edi, eax
0x14001440d  test    eax, eax
0x14001440f  js      loc_1400147DA
0x140014415  mov     eax, [rsi+10h]
0x140014418  mov     edx, [rsi+8]
0x14001441b  add     eax, 14h
0x14001441e  cmp     eax, edx
0x140014420  ja      loc_14001406A
0x140014426  mov     ecx, [rsi+0Ch]
0x140014429  lea     eax, [rdx+rcx]
0x14001442c  cmp     eax, [rsp+1B0h+var_164]
  ... truncated ...
```
