# JobStore::SetTaskCreationTime(JobMoniker &,DynamicTaskInfo *)

- ea: `0x18002d7ec`
- end: `0x18002db74`
- name: `?SetTaskCreationTime@JobStore@@QEAAJAEAVJobMoniker@@PEAUDynamicTaskInfo@@@Z`
- size: `904`
- prototype: `__int64 __fastcall(JobStore *__hidden this, struct JobMoniker *, struct DynamicTaskInfo *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002cd8c`
- `0x18004191c`

## callees

- `0x18000e510`
- `0x180021300`
- `0x18002d7ec`
- `0x18002dce0`
- `0x18003fff0`
- `0x180042950`
- `0x18004a494`
- `0x180070200`

## import_xrefs

- `msvcrt!rand` at `0x18002dab5`
- `msvcrt!rand` at `0x18002dab5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dafe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dafe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d88b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002d88b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db50`

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
0x18002d7ec  mov     [rsp-8+arg_0], rbx
0x18002d7f1  mov     [rsp-8+arg_8], rsi
0x18002d7f6  push    rbp
0x18002d7f7  push    rdi
0x18002d7f8  push    r12
0x18002d7fa  push    r14
0x18002d7fc  push    r15
0x18002d7fe  lea     rbp, [rsp-37h]
0x18002d803  sub     rsp, 90h
0x18002d80a  mov     rsi, r8
0x18002d80d  mov     r14, rdx
0x18002d810  mov     r15, rcx
0x18002d813  mov     qword ptr [rbp+57h+Data], 3
0x18002d81b  xor     r12d, r12d
0x18002d81e  mov     qword ptr [rbp+57h+var_40+4], r12
0x18002d822  mov     qword ptr [rbp+57h+Data+8], r12
0x18002d826  mov     qword ptr [rbp+57h+var_40+0Ch], r12
0x18002d82a  mov     dword ptr [rbp+57h+var_40], r12d
0x18002d82e  mov     ebx, r12d
0x18002d831  mov     [rbp+57h+Type], rbx
0x18002d835  mov     [rbp+57h+hKey], r12
0x18002d839  mov     r9d, 2001Bh; unsigned int
0x18002d83f  lea     r8, [rbp+57h+hKey]; HKEY *
0x18002d843  call    ?RegOpenTaskKey@JobStore@@QEAAJAEAVJobMoniker@@PEAPEAUHKEY__@@K@Z; JobStore::RegOpenTaskKey(JobMoniker &,HKEY__ * *,ulong)
0x18002d848  mov     edi, eax
0x18002d84a  test    eax, eax
0x18002d84c  jns     short loc_18002D85C
0x18002d84e  lea     rcx, [rbp+57h+hKey]; this
0x18002d852  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18002d857  jmp     loc_18002DB48
0x18002d85c  mov     dword ptr [rbp+57h+Type], r12d
0x18002d860  mov     [rbp+57h+cbData], 24h ; '$'
0x18002d867  lea     rax, [rbp+57h+cbData]
0x18002d86b  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x18002d870  lea     rax, [rbp+57h+Data]
0x18002d874  mov     [rsp+0B0h+lpData], rax; lpData
0x18002d879  lea     r9, [rbp+57h+Type]; lpType
0x18002d87d  xor     r8d, r8d; lpReserved
0x18002d880  lea     rdx, aDynamicinfo; "DynamicInfo"
0x18002d887  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d88b  call    cs:__imp_RegQueryValueExW
0x18002d891  mov     edi, eax
0x18002d893  test    eax, eax
0x18002d895  jz      short loc_18002D8CF
0x18002d897  cmp     eax, 2
0x18002d89a  jnz     short loc_18002D8B8
0x18002d89c  mov     qword ptr [rbp+57h+Data+4], r12
0x18002d8a0  xorps   xmm0, xmm0
0x18002d8a3  movdqu  xmmword ptr [rbp+57h+Data+0Ch], xmm0
0x18002d8a8  mov     qword ptr [rbp+57h+var_40+0Ch], r12
0x18002d8ac  mov     dword ptr [rbp+57h+Data], 3
0x18002d8b3  lea     edi, [rax-1]
0x18002d8b6  jmp     short loc_18002D8E6
0x18002d8b8  test    eax, eax
0x18002d8ba  jle     short loc_18002D8C5
0x18002d8bc  movzx   edi, ax
0x18002d8bf  or      edi, 80070000h
0x18002d8c5  test    edi, edi
0x18002d8c7  js      loc_18002DB38
0x18002d8cd  jmp     short loc_18002D8E6
0x18002d8cf  cmp     dword ptr [rbp+57h+Type], 3
0x18002d8d3  jnz     loc_18002DB33
0x18002d8d9  cmp     dword ptr [rbp+57h+Data], 3
0x18002d8dd  jnz     loc_18002DB33
0x18002d8e3  mov     edi, r12d
0x18002d8e6  mov     rbx, [rbp+57h+hKey]
0x18002d8ea  mov     [rbp+57h+Type], rbx
0x18002d8ee  cmp     edi, 1
0x18002d8f1  jz      loc_18002D995
0x18002d8f7  cmp     dword ptr [rbp+57h+Data+8], r12d
0x18002d8fb  jnz     short loc_18002D907
0x18002d8fd  cmp     dword ptr [rbp+57h+Data+4], r12d
0x18002d901  jz      loc_18002D995
0x18002d907  mov     rax, [r14+20h]
0x18002d90b  mov     rcx, [rax+0D0h]
0x18002d912  test    rcx, rcx
0x18002d915  jz      short loc_18002D945
0x18002d917  movsd   xmm0, qword ptr [rcx+38h]
0x18002d91c  movsd   [rbp+57h+hKey], xmm0
0x18002d921  mov     eax, [rcx+40h]
0x18002d924  mov     [rbp+57h+var_70], eax
0x18002d927  movzx   r11d, word ptr [rcx+44h]
0x18002d92c  movzx   r10d, word ptr [rbp+57h+var_70+2]
0x18002d931  movzx   r9d, word ptr [rbp+57h+hKey+6]
0x18002d936  movzx   r8d, word ptr [rbp+57h+hKey+4]
0x18002d93b  movzx   edx, word ptr [rbp+57h+hKey+2]
0x18002d93f  movzx   ecx, word ptr [rbp+57h+hKey]
0x18002d943  jmp     short loc_18002D95A
0x18002d945  mov     ecx, r12d
0x18002d948  mov     edx, r12d
0x18002d94b  mov     r8d, r12d
0x18002d94e  mov     r9d, r12d
0x18002d951  mov     eax, r12d
0x18002d954  mov     r10d, r12d
0x18002d957  mov     r11d, r12d
0x18002d95a  test    cx, cx
0x18002d95d  jnz     short loc_18002D985
0x18002d95f  test    dx, dx
0x18002d962  jnz     short loc_18002D985
0x18002d964  test    r8w, r8w
0x18002d968  jnz     short loc_18002D985
0x18002d96a  test    r9w, r9w
0x18002d96e  jnz     short loc_18002D985
0x18002d970  test    ax, ax
0x18002d973  jnz     short loc_18002D985
0x18002d975  test    r10w, r10w
0x18002d979  jnz     short loc_18002D985
0x18002d97b  test    r11w, r11w
0x18002d97f  jz      loc_18002DB17
0x18002d985  mov     rcx, r15; this
0x18002d988  call    ?IsMTRCompleted@JobStore@@QEBAHXZ; JobStore::IsMTRCompleted(void)
0x18002d98d  test    eax, eax
0x18002d98f  jnz     loc_18002DB17
0x18002d995  mov     byte ptr [rbp+57h+var_60], r12b
0x18002d999  mov     rax, qword ptr [rbp+57h+Data+4]
0x18002d99d  mov     qword ptr [rbp+57h+var_60+8], rax
0x18002d9a1  shr     rax, 20h
0x18002d9a5  test    eax, eax
0x18002d9a7  jnz     short loc_18002D9C1
0x18002d9a9  cmp     dword ptr [rbp+57h+Data+4], r12d
0x18002d9ad  jnz     short loc_18002D9C1
0x18002d9af  lea     rcx, [rbp+57h+var_60]; this
0x18002d9b3  call    ??0TSTime@@QEAA@_N@Z; TSTime::TSTime(bool)
0x18002d9b8  movaps  xmm0, [rbp+57h+var_60]
0x18002d9bc  movdqa  [rbp+57h+var_60], xmm0
0x18002d9c1  mov     rax, [r14+20h]
0x18002d9c5  mov     rcx, [rax+0D0h]
0x18002d9cc  test    rcx, rcx
0x18002d9cf  jz      short loc_18002D9EB
0x18002d9d1  movsd   xmm0, qword ptr [rcx+38h]
0x18002d9d6  movsd   [rbp+57h+hKey], xmm0
0x18002d9db  mov     eax, [rcx+40h]
0x18002d9de  mov     [rbp+57h+var_70], eax
0x18002d9e1  movzx   eax, word ptr [rcx+44h]
0x18002d9e5  mov     [rbp+57h+var_6C], ax
0x18002d9e9  jmp     short loc_18002D9F8
0x18002d9eb  mov     [rbp+57h+hKey], r12
0x18002d9ef  mov     [rbp+57h+var_70], r12d
0x18002d9f3  mov     [rbp+57h+var_6C], r12w
0x18002d9f8  lea     rcx, [rbp+57h+hKey]; this
0x18002d9fc  call    ?IsEmpty@TSTimePeriod@@QEBA_NXZ; TSTimePeriod::IsEmpty(void)
0x18002da01  test    al, al
0x18002da03  jnz     loc_18002DAD2
0x18002da09  cmp     dword ptr [rbp+57h+Data+8], r12d
0x18002da0d  jnz     short loc_18002DA15
0x18002da0f  cmp     dword ptr [rbp+57h+Data+4], r12d
0x18002da13  jz      short loc_18002DA25
0x18002da15  mov     rcx, r15; this
0x18002da18  call    ?IsMTRCompleted@JobStore@@QEBAHXZ; JobStore::IsMTRCompleted(void)
0x18002da1d  test    eax, eax
0x18002da1f  jnz     loc_18002DAD2
0x18002da25  lea     rdx, [rbp+57h+hKey]
0x18002da29  mov     rcx, [r14+20h]
0x18002da2d  call    ?GetPeriodicity@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetPeriodicity(void)
0x18002da32  movzx   edx, word ptr [rax]
0x18002da35  lea     r8d, [rdx+rdx*2]
0x18002da39  movzx   eax, word ptr [rax+2]
0x18002da3d  lea     edx, [rax+r8*4]
0x18002da41  mov     rcx, [r14+20h]
0x18002da45  test    edx, edx
0x18002da47  lea     rdx, [rbp+57h+hKey]
0x18002da4b  jnz     short loc_18002DA97
0x18002da4d  call    ?GetPeriodicity@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetPeriodicity(void)
0x18002da52  movzx   ecx, word ptr [rax+4]
0x18002da56  imul    edx, ecx, 7
0x18002da59  movzx   ecx, word ptr [rax+6]
0x18002da5d  add     edx, ecx
0x18002da5f  lea     edx, [rdx+rdx*2]
0x18002da62  movzx   ecx, word ptr [rax+8]
0x18002da66  lea     edx, [rcx+rdx*8]
0x18002da69  imul    r8d, edx, 3Ch ; '<'
0x18002da6d  movzx   ecx, word ptr [rax+0Ah]
0x18002da71  add     r8d, ecx
0x18002da74  imul    ecx, r8d, 3Ch ; '<'
0x18002da78  movzx   eax, word ptr [rax+0Ch]
0x18002da7c  add     ecx, eax
0x18002da7e  movsxd  rcx, ecx
0x18002da81  mov     rax, 0C22E450672894AB7h
0x18002da8b  mul     rcx
0x18002da8e  mov     rdi, rdx
0x18002da91  shr     rdi, 10h
0x18002da95  jmp     short loc_18002DAAF
0x18002da97  call    ?GetPeriodicity@JobBucket@@QEBA?AVTSTimePeriod@@XZ; JobBucket::GetPeriodicity(void)
0x18002da9c  movzx   edx, word ptr [rax+2]
0x18002daa0  movzx   eax, word ptr [rax]
0x18002daa3  lea     rcx, [rax+rax*2]
0x18002daa7  lea     rax, [rdx+rcx*4]
0x18002daab  imul    rdi, rax, 1Ch
0x18002daaf  cmp     rdi, 1
0x18002dab3  jbe     short loc_18002DAD2
0x18002dab5  call    cs:__imp_rand
0x18002dabb  cdqe
0x18002dabd  xor     edx, edx
0x18002dabf  div     rdi
0x18002dac2  imul    rdx, 0FFFFFFFFFFFEAE80h
0x18002dac9  lea     rcx, [rbp+57h+var_60]
0x18002dacd  call    ??YTSTime@@QEAAAEBV0@_J@Z; TSTime::operator+=(__int64)
0x18002dad2  mov     rax, qword ptr [rbp+57h+var_60+8]
0x18002dad6  mov     qword ptr [rbp+57h+Data+4], rax
0x18002dada  mov     dword ptr [rsp+0B0h+lpcbData], 24h ; '$'; cbData
0x18002dae2  lea     rax, [rbp+57h+Data]
0x18002dae6  mov     [rsp+0B0h+lpData], rax; lpData
0x18002daeb  mov     r9d, 3; dwType
0x18002daf1  xor     r8d, r8d; Reserved
0x18002daf4  lea     rdx, aDynamicinfo; "DynamicInfo"
0x18002dafb  mov     rcx, rbx; hKey
0x18002dafe  call    cs:__imp_RegSetValueExW
0x18002db04  mov     edi, eax
0x18002db06  test    eax, eax
0x18002db08  jle     short loc_18002DB13
0x18002db0a  movzx   edi, ax
0x18002db0d  or      edi, 80070000h
0x18002db13  test    edi, edi
0x18002db15  js      short loc_18002DB48
0x18002db17  test    rsi, rsi
0x18002db1a  jz      short loc_18002DB48
0x18002db1c  movups  xmm0, xmmword ptr [rbp+57h+Data]
0x18002db20  movups  xmmword ptr [rsi], xmm0
0x18002db23  movups  xmm1, xmmword ptr [rbp+57h+var_40]
0x18002db27  movups  xmmword ptr [rsi+10h], xmm1
0x18002db2b  mov     eax, dword ptr [rbp+57h+var_40+10h]
0x18002db2e  mov     [rsi+20h], eax
0x18002db31  jmp     short loc_18002DB48
0x18002db33  mov     edi, 80041313h
0x18002db38  mov     rcx, [rbp+57h+hKey]; hKey
0x18002db3c  test    rcx, rcx
0x18002db3f  jz      short loc_18002DB48
0x18002db41  call    cs:__imp_RegCloseKey
0x18002db47  nop
0x18002db48  test    rbx, rbx
0x18002db4b  jz      short loc_18002DB56
0x18002db4d  mov     rcx, rbx; hKey
0x18002db50  call    cs:__imp_RegCloseKey
0x18002db56  mov     eax, edi
0x18002db58  lea     r11, [rsp+0B0h+var_20]
0x18002db60  mov     rbx, [r11+30h]
0x18002db64  mov     rsi, [r11+38h]
0x18002db68  mov     rsp, r11
0x18002db6b  pop     r15
0x18002db6d  pop     r14
0x18002db6f  pop     r12
0x18002db71  pop     rdi
0x18002db72  pop     rbp
0x18002db73  retn
```
