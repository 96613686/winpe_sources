# JobStore::SetTaskCreationTime(JobMoniker &,DynamicTaskInfo *)

- ea: `0x18000495c`
- end: `0x180004d03`
- name: `?SetTaskCreationTime@JobStore@@QEAAJAEAVJobMoniker@@PEAUDynamicTaskInfo@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(JobStore *__hidden this, struct JobMoniker *, struct DynamicTaskInfo *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003ec8`
- `0x180043e20`

## callees

- `0x18000495c`
- `0x180004d10`
- `0x18000ff10`
- `0x18000ff40`
- `0x18002db40`
- `0x180044980`
- `0x18004c80c`
- `0x180073acc`

## import_xrefs

- `msvcrt!rand` at `0x180004c2b`
- `msvcrt!rand` at `0x180004c2b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004c7a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180004c7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800049fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800049fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004cc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004cd8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004cc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004cd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JobStore::SetTaskCreationTime(HKEY *this, struct JobMoniker *a2, struct DynamicTaskInfo *a3)
{
  HKEY v6; // rbx
  int v7; // edi
  LSTATUS v8; // eax
  bool v9; // dl
  __int64 v10; // rcx
  int v11; // eax
  __int16 v12; // r11
  __int16 v13; // r10
  __int16 v14; // r9
  __int16 v15; // r8
  __int16 v16; // dx
  __int16 v17; // cx
  __int64 v18; // rcx
  unsigned __int16 *Periodicity; // rax
  __int64 v20; // rcx
  unsigned __int16 *v21; // rax
  unsigned __int64 v22; // rdi
  unsigned __int16 *v23; // rax
  int v24; // eax
  LSTATUS v25; // eax
  DWORD cbData; // [rsp+30h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-21h] BYREF
  int v29; // [rsp+40h] [rbp-19h]
  __int16 v30; // [rsp+44h] [rbp-15h]
  char v31; // [rsp+50h] [rbp-9h] BYREF
  __int64 v32; // [rsp+58h] [rbp-1h]
  _OWORD Data[3]; // [rsp+60h] [rbp+7h] BYREF
  HKEY Type; // [rsp+D8h] [rbp+7Fh] BYREF

  *(_QWORD *)&Data[0] = 3;
  memset((char *)Data + 8, 0, 28);
  v6 = 0;
  Type = 0;
  hKey = 0;
  v7 = JobStore::RegOpenTaskKey(this, a2, &hKey, 0x2001Bu);
  if ( v7 < 0 )
  {
    wmi::AutoRegKey::Close((wmi::AutoRegKey *)&hKey);
    goto LABEL_47;
  }
  LODWORD(Type) = 0;
  cbData = 36;
  v8 = RegQueryValueExW(hKey, L"DynamicInfo", 0, (LPDWORD)&Type, (LPBYTE)Data, &cbData);
  v7 = v8;
  if ( v8 )
  {
    if ( v8 == 2 )
    {
      memset((char *)Data + 4, 0, 32);
      LODWORD(Data[0]) = 3;
      v7 = 1;
LABEL_13:
      v6 = hKey;
      Type = hKey;
      if ( v7 != 1 && *(_QWORD *)((char *)Data + 4) )
      {
        v10 = *(_QWORD *)(*((_QWORD *)a2 + 4) + 208LL);
        if ( v10 )
        {
          hKey = *(HKEY *)(v10 + 56);
          v11 = *(_DWORD *)(v10 + 64);
          v29 = v11;
          v12 = *(_WORD *)(v10 + 68);
          v13 = HIWORD(v11);
          v14 = HIWORD(hKey);
          v15 = WORD2(hKey);
          v16 = WORD1(hKey);
          v17 = (__int16)hKey;
        }
        else
        {
          v17 = 0;
          v16 = 0;
          v15 = 0;
          v14 = 0;
          LOWORD(v11) = 0;
          v13 = 0;
          v12 = 0;
        }
        if ( !v17 && !v16 && !v15 && !v14 && !(_WORD)v11 && !v13 && !v12
          || (unsigned int)JobStore::IsMTRCompleted((JobStore *)this) )
        {
          goto LABEL_42;
        }
      }
      v31 = 0;
      v32 = *(_QWORD *)((char *)Data + 4);
      if ( !*(_QWORD *)((char *)Data + 4) )
        TSTime::TSTime((TSTime *)&v31, v9);
      v18 = *(_QWORD *)(*((_QWORD *)a2 + 4) + 208LL);
      if ( v18 )
      {
        hKey = *(HKEY *)(v18 + 56);
        v29 = *(_DWORD *)(v18 + 64);
        v30 = *(_WORD *)(v18 + 68);
      }
      else
      {
        hKey = 0;
        v29 = 0;
        v30 = 0;
      }
      if ( !TSTimePeriod::IsEmpty((TSTimePeriod *)&hKey)
        && (!*(_QWORD *)((char *)Data + 4) || !(unsigned int)JobStore::IsMTRCompleted((JobStore *)this)) )
      {
        Periodicity = (unsigned __int16 *)JobBucket::GetPeriodicity(*((_QWORD *)a2 + 4), &hKey);
        v20 = *((_QWORD *)a2 + 4);
        if ( Periodicity[1] + 12 * *Periodicity )
        {
          v23 = (unsigned __int16 *)JobBucket::GetPeriodicity(v20, &hKey);
          v22 = 28 * (v23[1] + 12LL * *v23);
        }
        else
        {
          v21 = (unsigned __int16 *)JobBucket::GetPeriodicity(v20, &hKey);
          v22 = (v21[6] + 60 * (v21[5] + 60 * (v21[4] + 24 * (v21[3] + 7 * v21[2])))) / 0x15180uLL;
        }
        if ( v22 > 1 )
        {
          v24 = rand();
          TSTime::operator+=(&v31, -86400LL * (v24 % v22));
        }
      }
      *(_QWORD *)((char *)Data + 4) = v32;
      v25 = RegSetValueExW(v6, L"DynamicInfo", 0, 3u, (const BYTE *)Data, 0x24u);
      v7 = v25;
      if ( v25 > 0 )
        v7 = (unsigned __int16)v25 | 0x80070000;
      if ( v7 >= 0 )
      {
LABEL_42:
        if ( a3 )
        {
          *(_OWORD *)a3 = Data[0];
          *((_OWORD *)a3 + 1) = Data[1];
          *((_DWORD *)a3 + 8) = Data[2];
        }
      }
      goto LABEL_47;
    }
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 >= 0 )
      goto LABEL_13;
  }
  else
  {
    if ( (_DWORD)Type == 3 && LODWORD(Data[0]) == 3 )
    {
      v7 = 0;
      goto LABEL_13;
    }
    v7 = -2147216621;
  }
  if ( hKey )
    RegCloseKey(hKey);
LABEL_47:
  if ( v6 )
    RegCloseKey(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000495c  mov     [rsp-8+arg_0], rbx
0x180004961  mov     [rsp-8+arg_8], rsi
0x180004966  push    rbp
0x180004967  push    rdi
0x180004968  push    r12
0x18000496a  push    r14
0x18000496c  push    r15
0x18000496e  lea     rbp, [rsp-37h]
0x180004973  sub     rsp, 90h
0x18000497a  mov     rsi, r8
0x18000497d  mov     r14, rdx
0x180004980  mov     r15, rcx
0x180004983  mov     qword ptr [rbp+57h+Data], 3
0x18000498b  xor     r12d, r12d
0x18000498e  mov     qword ptr [rbp+57h+var_40+4], r12
0x180004992  mov     qword ptr [rbp+57h+Data+8], r12
0x180004996  mov     qword ptr [rbp+57h+var_40+0Ch], r12
0x18000499a  mov     dword ptr [rbp+57h+var_40], r12d
0x18000499e  mov     ebx, r12d
0x1800049a1  mov     [rbp+57h+Type], rbx
0x1800049a5  mov     [rbp+57h+hKey], r12
0x1800049a9  mov     r9d, 2001Bh; unsigned int
0x1800049af  lea     r8, [rbp+57h+hKey]; HKEY *
0x1800049b3  call    ?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z; JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)
0x1800049b8  mov     edi, eax
0x1800049ba  test    eax, eax
0x1800049bc  jns     short loc_1800049CC
0x1800049be  lea     rcx, [rbp+57h+hKey]; this
0x1800049c2  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x1800049c7  jmp     loc_180004CD0
0x1800049cc  mov     dword ptr [rbp+57h+Type], r12d
0x1800049d0  mov     [rbp+57h+cbData], 24h ; '$'
0x1800049d7  lea     rax, [rbp+57h+cbData]
0x1800049db  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x1800049e0  lea     rax, [rbp+57h+Data]
0x1800049e4  mov     [rsp+0B0h+lpData], rax; lpData
0x1800049e9  lea     r9, [rbp+57h+Type]; lpType
0x1800049ed  xor     r8d, r8d; lpReserved
0x1800049f0  lea     rdx, ValueName; "DynamicInfo"
0x1800049f7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800049fb  call    cs:__imp_RegQueryValueExW
0x180004a02  nop     dword ptr [rax+rax+00h]
0x180004a07  mov     edi, eax
0x180004a09  test    eax, eax
0x180004a0b  jz      short loc_180004A45
0x180004a0d  cmp     eax, 2
0x180004a10  jnz     short loc_180004A2E
0x180004a12  mov     qword ptr [rbp+57h+Data+4], r12
0x180004a16  xorps   xmm0, xmm0
0x180004a19  movdqu  xmmword ptr [rbp+57h+Data+0Ch], xmm0
0x180004a1e  mov     qword ptr [rbp+57h+var_40+0Ch], r12
0x180004a22  mov     dword ptr [rbp+57h+Data], 3
0x180004a29  lea     edi, [rax-1]
0x180004a2c  jmp     short loc_180004A5C
0x180004a2e  test    eax, eax
0x180004a30  jle     short loc_180004A3B
0x180004a32  movzx   edi, ax
0x180004a35  or      edi, 80070000h
0x180004a3b  test    edi, edi
0x180004a3d  js      loc_180004CBA
0x180004a43  jmp     short loc_180004A5C
0x180004a45  cmp     dword ptr [rbp+57h+Type], 3
0x180004a49  jnz     loc_180004CB5
0x180004a4f  cmp     dword ptr [rbp+57h+Data], 3
0x180004a53  jnz     loc_180004CB5
0x180004a59  mov     edi, r12d
0x180004a5c  mov     rbx, [rbp+57h+hKey]
0x180004a60  mov     [rbp+57h+Type], rbx
0x180004a64  cmp     edi, 1
0x180004a67  jz      loc_180004B0B
0x180004a6d  cmp     dword ptr [rbp+57h+Data+8], r12d
0x180004a71  jnz     short loc_180004A7D
0x180004a73  cmp     dword ptr [rbp+57h+Data+4], r12d
0x180004a77  jz      loc_180004B0B
0x180004a7d  mov     rax, [r14+20h]
0x180004a81  mov     rcx, [rax+0D0h]
0x180004a88  test    rcx, rcx
0x180004a8b  jz      short loc_180004ABB
0x180004a8d  movsd   xmm0, qword ptr [rcx+38h]
0x180004a92  movsd   [rbp+57h+hKey], xmm0
0x180004a97  mov     eax, [rcx+40h]
0x180004a9a  mov     [rbp+57h+var_70], eax
0x180004a9d  movzx   r11d, word ptr [rcx+44h]
0x180004aa2  movzx   r10d, word ptr [rbp+57h+var_70+2]
0x180004aa7  movzx   r9d, word ptr [rbp+57h+hKey+6]
0x180004aac  movzx   r8d, word ptr [rbp+57h+hKey+4]
0x180004ab1  movzx   edx, word ptr [rbp+57h+hKey+2]
0x180004ab5  movzx   ecx, word ptr [rbp+57h+hKey]
0x180004ab9  jmp     short loc_180004AD0
0x180004abb  mov     ecx, r12d
0x180004abe  mov     edx, r12d
0x180004ac1  mov     r8d, r12d
0x180004ac4  mov     r9d, r12d
0x180004ac7  mov     eax, r12d
0x180004aca  mov     r10d, r12d
0x180004acd  mov     r11d, r12d
0x180004ad0  test    cx, cx
0x180004ad3  jnz     short loc_180004AFB
0x180004ad5  test    dx, dx
0x180004ad8  jnz     short loc_180004AFB
0x180004ada  test    r8w, r8w
0x180004ade  jnz     short loc_180004AFB
0x180004ae0  test    r9w, r9w
0x180004ae4  jnz     short loc_180004AFB
0x180004ae6  test    ax, ax
0x180004ae9  jnz     short loc_180004AFB
0x180004aeb  test    r10w, r10w
0x180004aef  jnz     short loc_180004AFB
0x180004af1  test    r11w, r11w
0x180004af5  jz      loc_180004C99
0x180004afb  mov     rcx, r15; this
0x180004afe  call    ?IsMTRCompleted@JobStore@@QEBAHXZ; JobStore::IsMTRCompleted(void)
0x180004b03  test    eax, eax
0x180004b05  jnz     loc_180004C99
0x180004b0b  mov     byte ptr [rbp+57h+var_60], r12b
0x180004b0f  mov     rax, qword ptr [rbp+57h+Data+4]
0x180004b13  mov     qword ptr [rbp+57h+var_60+8], rax
0x180004b17  shr     rax, 20h
0x180004b1b  test    eax, eax
0x180004b1d  jnz     short loc_180004B37
0x180004b1f  cmp     dword ptr [rbp+57h+Data+4], r12d
0x180004b23  jnz     short loc_180004B37
0x180004b25  lea     rcx, [rbp+57h+var_60]; this
0x180004b29  call    ??0TSTime@@QEAA@_N@Z; TSTime::TSTime(bool)
0x180004b2e  movaps  xmm0, [rbp+57h+var_60]
0x180004b32  movdqa  [rbp+57h+var_60], xmm0
0x180004b37  mov     rax, [r14+20h]
0x180004b3b  mov     rcx, [rax+0D0h]
0x180004b42  test    rcx, rcx
0x180004b45  jz      short loc_180004B61
0x180004b47  movsd   xmm0, qword ptr [rcx+38h]
0x180004b4c  movsd   [rbp+57h+hKey], xmm0
0x180004b51  mov     eax, [rcx+40h]
0x180004b54  mov     [rbp+57h+var_70], eax
0x180004b57  movzx   eax, word ptr [rcx+44h]
0x180004b5b  mov     [rbp+57h+var_6C], ax
0x180004b5f  jmp     short loc_180004B6E
0x180004b61  mov     [rbp+57h+hKey], r12
0x180004b65  mov     [rbp+57h+var_70], r12d
0x180004b69  mov     [rbp+57h+var_6C], r12w
0x180004b6e  lea     rcx, [rbp+57h+hKey]; this
0x180004b72  call    ?IsEmpty@TSTimePeriod@@QEBA_NXZ; TSTimePeriod::IsEmpty(void)
0x180004b77  test    al, al
0x180004b79  jnz     loc_180004C4E
0x180004b7f  cmp     dword ptr [rbp+57h+Data+8], r12d
0x180004b83  jnz     short loc_180004B8B
0x180004b85  cmp     dword ptr [rbp+57h+Data+4], r12d
0x180004b89  jz      short loc_180004B9B
0x180004b8b  mov     rcx, r15; this
0x180004b8e  call    ?IsMTRCompleted@JobStore@@QEBAHXZ; JobStore::IsMTRCompleted(void)
0x180004b93  test    eax, eax
0x180004b95  jnz     loc_180004C4E
0x180004b9b  lea     rdx, [rbp+57h+hKey]
0x180004b9f  mov     rcx, [r14+20h]
0x180004ba3  call    ?GetPeriodicity@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetPeriodicity(void)
0x180004ba8  movzx   edx, word ptr [rax]
0x180004bab  lea     r8d, [rdx+rdx*2]
0x180004baf  movzx   eax, word ptr [rax+2]
0x180004bb3  lea     edx, [rax+r8*4]
0x180004bb7  mov     rcx, [r14+20h]
0x180004bbb  test    edx, edx
0x180004bbd  lea     rdx, [rbp+57h+hKey]
0x180004bc1  jnz     short loc_180004C0D
0x180004bc3  call    ?GetPeriodicity@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetPeriodicity(void)
0x180004bc8  movzx   ecx, word ptr [rax+4]
0x180004bcc  imul    edx, ecx, 7
0x180004bcf  movzx   ecx, word ptr [rax+6]
0x180004bd3  add     edx, ecx
0x180004bd5  lea     edx, [rdx+rdx*2]
0x180004bd8  movzx   ecx, word ptr [rax+8]
0x180004bdc  lea     edx, [rcx+rdx*8]
0x180004bdf  imul    r8d, edx, 3Ch ; '<'
0x180004be3  movzx   ecx, word ptr [rax+0Ah]
0x180004be7  add     r8d, ecx
0x180004bea  imul    ecx, r8d, 3Ch ; '<'
0x180004bee  movzx   eax, word ptr [rax+0Ch]
0x180004bf2  add     ecx, eax
0x180004bf4  movsxd  rcx, ecx
0x180004bf7  mov     rax, 0C22E450672894AB7h
0x180004c01  mul     rcx
0x180004c04  mov     rdi, rdx
0x180004c07  shr     rdi, 10h
0x180004c0b  jmp     short loc_180004C25
0x180004c0d  call    ?GetPeriodicity@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetPeriodicity(void)
0x180004c12  movzx   edx, word ptr [rax+2]
0x180004c16  movzx   eax, word ptr [rax]
0x180004c19  lea     rcx, [rax+rax*2]
0x180004c1d  lea     rax, [rdx+rcx*4]
0x180004c21  imul    rdi, rax, 1Ch
0x180004c25  cmp     rdi, 1
0x180004c29  jbe     short loc_180004C4E
0x180004c2b  call    cs:__imp_rand
0x180004c32  nop     dword ptr [rax+rax+00h]
0x180004c37  cdqe
0x180004c39  xor     edx, edx
0x180004c3b  div     rdi
0x180004c3e  imul    rdx, 0FFFFFFFFFFFEAE80h
0x180004c45  lea     rcx, [rbp+57h+var_60]
0x180004c49  call    ??YTSTime@@QEAAAEBV0@_J@Z; TSTime::operator+=(__int64)
0x180004c4e  mov     rax, qword ptr [rbp+57h+var_60+8]
0x180004c52  mov     qword ptr [rbp+57h+Data+4], rax
0x180004c56  mov     dword ptr [rsp+0B0h+lpcbData], 24h ; '$'; cbData
0x180004c5e  lea     rax, [rbp+57h+Data]
0x180004c62  mov     [rsp+0B0h+lpData], rax; lpData
0x180004c67  mov     r9d, 3; dwType
0x180004c6d  xor     r8d, r8d; Reserved
0x180004c70  lea     rdx, ValueName; "DynamicInfo"
0x180004c77  mov     rcx, rbx; hKey
0x180004c7a  call    cs:__imp_RegSetValueExW
0x180004c81  nop     dword ptr [rax+rax+00h]
0x180004c86  mov     edi, eax
0x180004c88  test    eax, eax
0x180004c8a  jle     short loc_180004C95
0x180004c8c  movzx   edi, ax
0x180004c8f  or      edi, 80070000h
0x180004c95  test    edi, edi
0x180004c97  js      short loc_180004CD0
0x180004c99  test    rsi, rsi
0x180004c9c  jz      short loc_180004CD0
0x180004c9e  movups  xmm0, xmmword ptr [rbp+57h+Data]
0x180004ca2  movups  xmmword ptr [rsi], xmm0
0x180004ca5  movups  xmm1, xmmword ptr [rbp+57h+var_40]
0x180004ca9  movups  xmmword ptr [rsi+10h], xmm1
0x180004cad  mov     eax, dword ptr [rbp+57h+var_40+10h]
0x180004cb0  mov     [rsi+20h], eax
0x180004cb3  jmp     short loc_180004CD0
0x180004cb5  mov     edi, 80041313h
0x180004cba  mov     rcx, [rbp+57h+hKey]; hKey
0x180004cbe  test    rcx, rcx
0x180004cc1  jz      short loc_180004CD0
0x180004cc3  call    cs:__imp_RegCloseKey
0x180004cca  nop     dword ptr [rax+rax+00h]
0x180004ccf  nop
0x180004cd0  test    rbx, rbx
0x180004cd3  jz      short loc_180004CE4
0x180004cd5  mov     rcx, rbx; hKey
0x180004cd8  call    cs:__imp_RegCloseKey
0x180004cdf  nop     dword ptr [rax+rax+00h]
0x180004ce4  mov     eax, edi
0x180004ce6  lea     r11, [rsp+0B0h+var_20]
0x180004cee  mov     rbx, [r11+30h]
0x180004cf2  mov     rsi, [r11+38h]
0x180004cf6  mov     rsp, r11
0x180004cf9  pop     r15
0x180004cfb  pop     r14
0x180004cfd  pop     r12
0x180004cff  pop     rdi
0x180004d00  pop     rbp
0x180004d01  retn
```
