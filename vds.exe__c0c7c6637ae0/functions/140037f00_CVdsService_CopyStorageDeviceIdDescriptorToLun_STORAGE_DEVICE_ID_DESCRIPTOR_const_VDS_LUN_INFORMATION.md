# CVdsService::CopyStorageDeviceIdDescriptorToLun(_STORAGE_DEVICE_ID_DESCRIPTOR const *,_VDS_LUN_INFORMATION *)

- ea: `0x140037f00`
- end: `0x14003819e`
- name: `?CopyStorageDeviceIdDescriptorToLun@CVdsService@@CAJPEBU_STORAGE_DEVICE_ID_DESCRIPTOR@@PEAU_VDS_LUN_INFORMATION@@@Z`
- size: `670`
- prototype: `__int64 __fastcall(const struct _STORAGE_DEVICE_ID_DESCRIPTOR *, struct _VDS_LUN_INFORMATION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140025e20`

## callees

- `0x14002de26`
- `0x14002e123`
- `0x140037f00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140038006`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003808d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140038006`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003808d`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140037f26`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140037f26`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140038187`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140038187`
- `vdsutil!VdsTraceW` at `0x140037f56`
- `vdsutil!VdsTraceW` at `0x140037fbc`
- `vdsutil!VdsTraceW` at `0x140037fdb`
- `vdsutil!VdsTraceW` at `0x140037ff3`
- `vdsutil!VdsTraceW` at `0x1400380da`
- `vdsutil!VdsTraceW` at `0x1400380fc`
- `vdsutil!VdsTraceW` at `0x140038162`
- `vdsutil!VdsTraceW` at `0x14003817b`
- `vdsutil!VdsTraceW` at `0x140037f56`
- `vdsutil!VdsTraceW` at `0x140037fbc`
- `vdsutil!VdsTraceW` at `0x140037fdb`
- `vdsutil!VdsTraceW` at `0x140037ff3`
- `vdsutil!VdsTraceW` at `0x1400380da`
- `vdsutil!VdsTraceW` at `0x1400380fc`
- `vdsutil!VdsTraceW` at `0x140038162`
- `vdsutil!VdsTraceW` at `0x14003817b`

## string_xrefs

- `0x140037f15`: `CVdsService::CopyStorageDeviceIdDescriptorToLun`
- `0x140038172`: `CVdsService::CopyStorageDeviceIdDescriptorToLun, 1, hr=%lX`
- `0x140037f48`: `CVdsService::CopyStorageDeviceIdDescriptorToLun, 2, Count=%ld`
- `0x140037fb2`: `CVdsService::CopyStorageDeviceIdDescriptorToLun, 4, size=%ld, offset=%ld, count=%ld, assoc count=%ld, version=%lu`
- `0x140037fd1`: `CVdsService::CopyStorageDeviceIdDescriptorToLun, 5, Device Assoc. Count=%ld`
- `0x140037fe9`: `CVdsService::CopyStorageDeviceIdDescriptorToLun, 6, Device Assoc. Count=%ld`
- `0x14003801e`: `CVdsService::CopyStorageDeviceIdDescriptorToLun, 7, hr=%lX`
- `0x140038159`: `CVdsService::CopyStorageDeviceIdDescriptorToLun, 8, field offset:%lX, Id size:%lX, Next:%lX, Index:%lu, dwIdCount:%lu, hr=%lX`
- `0x14003812d`: `CVdsService::CopyStorageDeviceIdDescriptorToLun, 9, hr=%lX`
- `0x1400380d0`: `CVdsService::CopyStorageDeviceIdDescriptorToLun, 10, Assoc=%ld, Type=%ld, CodeSet=%ld, size=%lu`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVdsService::CopyStorageDeviceIdDescriptorToLun(
        const struct _STORAGE_DEVICE_ID_DESCRIPTOR *a1,
        struct _VDS_LUN_INFORMATION *a2)
{
  ULONG v4; // edi
  DWORD NumberOfIdentifiers; // r15d
  BYTE *Identifiers; // rbx
  BYTE *v7; // rcx
  DWORD i; // edx
  ULONG v9; // eax
  unsigned int v10; // esi
  SIZE_T v11; // rdi
  VDS_STORAGE_IDENTIFIER *v12; // rax
  VDS_STORAGE_IDENTIFIER *m_rgIdentifiers; // rdi
  DWORD v14; // ebp
  int v15; // edx
  __int64 v16; // r9
  BYTE *v17; // rcx
  unsigned __int8 *m_rgbIdentifier; // r14
  ULONG j; // r12d
  __int64 v21; // [rsp+20h] [rbp-68h]
  __int64 v22; // [rsp+28h] [rbp-60h]
  _BYTE v23[72]; // [rsp+40h] [rbp-48h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v23, 0x5Eu, "CVdsService::CopyStorageDeviceIdDescriptorToLun");
  if ( a1 && a2 )
  {
    v4 = 0;
    NumberOfIdentifiers = a1->NumberOfIdentifiers;
    VdsTraceW(2, L"CVdsService::CopyStorageDeviceIdDescriptorToLun, 2, Count=%ld", NumberOfIdentifiers);
    Identifiers = a1->Identifiers;
    v7 = a1->Identifiers;
    for ( i = 0; i < NumberOfIdentifiers; ++i )
    {
      v9 = v4 + 1;
      if ( *((_DWORD *)v7 + 3) )
        v9 = v4;
      v4 = v9;
      v7 += *((unsigned __int16 *)v7 + 5);
    }
    a2->m_deviceIdDescriptor.m_version = a1->Version;
    v10 = 0;
    if ( a1->Size >= 0xC )
    {
      a2->m_deviceIdDescriptor.m_cIdentifiers = v4;
      if ( v4 )
      {
        VdsTraceW(2, L"CVdsService::CopyStorageDeviceIdDescriptorToLun, 6, Device Assoc. Count=%ld", v4);
        v11 = 24LL * v4;
        v12 = (VDS_STORAGE_IDENTIFIER *)CoTaskMemAlloc(v11);
        a2->m_deviceIdDescriptor.m_rgIdentifiers = v12;
        if ( v12 )
        {
          memset_0(v12, 0, v11);
          m_rgIdentifiers = a2->m_deviceIdDescriptor.m_rgIdentifiers;
          v14 = 0;
          while ( v14 < NumberOfIdentifiers )
          {
            if ( *((_DWORD *)Identifiers + 3) )
            {
              Identifiers += *((unsigned __int16 *)Identifiers + 5);
              ++v14;
            }
            else
            {
              m_rgIdentifiers->m_Type = *((_DWORD *)Identifiers + 1);
              m_rgIdentifiers->m_CodeSet = *(_DWORD *)Identifiers;
              v15 = *((unsigned __int16 *)Identifiers + 4);
              if ( !(_WORD)v15 )
              {
                v16 = *((unsigned __int16 *)Identifiers + 4);
LABEL_26:
                v10 = -2147418113;
                LODWORD(v22) = v14;
                LODWORD(v21) = *((unsigned __int16 *)Identifiers + 5);
                VdsTraceW(
                  0,
                  L"CVdsService::CopyStorageDeviceIdDescriptorToLun, 8, field offset:%lX, Id size:%lX, Next:%lX, Index:%lu"
                   ", dwIdCount:%lu, hr=%lX",
                  16,
                  v16,
                  v21,
                  v22,
                  NumberOfIdentifiers,
                  -2147418113);
                break;
              }
              if ( v14 + 1 != NumberOfIdentifiers )
              {
                v16 = *((unsigned __int16 *)Identifiers + 4);
                if ( v15 + 16 > (unsigned int)*((unsigned __int16 *)Identifiers + 5) )
                  goto LABEL_26;
              }
              v17 = (BYTE *)CoTaskMemAlloc(*((unsigned __int16 *)Identifiers + 4));
              m_rgIdentifiers->m_rgbIdentifier = v17;
              if ( !v17 )
              {
                v10 = -2147024882;
                VdsTraceW(0, L"CVdsService::CopyStorageDeviceIdDescriptorToLun, 9, hr=%lX");
                break;
              }
              ++v14;
              m_rgIdentifiers->m_cbIdentifier = *((unsigned __int16 *)Identifiers + 4);
              memcpy_0(v17, Identifiers + 16, *((unsigned __int16 *)Identifiers + 4));
              LODWORD(v22) = m_rgIdentifiers->m_cbIdentifier;
              LODWORD(v21) = m_rgIdentifiers->m_CodeSet;
              VdsTraceW(
                2,
                L"CVdsService::CopyStorageDeviceIdDescriptorToLun, 10, Assoc=%ld, Type=%ld, CodeSet=%ld, size=%lu",
                *((unsigned int *)Identifiers + 3),
                (unsigned int)m_rgIdentifiers->m_Type,
                v21,
                v22);
              m_rgbIdentifier = m_rgIdentifiers->m_rgbIdentifier;
              for ( j = 0; j < m_rgIdentifiers->m_cbIdentifier; ++j )
                VdsTraceW(2, L"ID identifier={%.2x}", *m_rgbIdentifier++);
              Identifiers += *((unsigned __int16 *)Identifiers + 5);
              ++m_rgIdentifiers;
            }
          }
        }
        else
        {
          v10 = -2147024882;
          VdsTraceW(0, L"CVdsService::CopyStorageDeviceIdDescriptorToLun, 7, hr=%lX");
        }
      }
      else
      {
        VdsTraceW(1, L"CVdsService::CopyStorageDeviceIdDescriptorToLun, 5, Device Assoc. Count=%ld", 0);
      }
    }
    else
    {
      a2->m_deviceIdDescriptor.m_cIdentifiers = 0;
      VdsTraceW(
        2,
        L"CVdsService::CopyStorageDeviceIdDescriptorToLun, 4, size=%ld, offset=%ld, count=%ld, assoc count=%ld, version=%lu",
        a1->Size);
    }
  }
  else
  {
    v10 = -2147024809;
    VdsTraceW(0, L"CVdsService::CopyStorageDeviceIdDescriptorToLun, 1, hr=%lX");
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v23);
  return v10;
}

```

## disassembly

```asm
0x140037f00  push    rbx
0x140037f02  push    rbp
0x140037f03  push    rsi
0x140037f04  push    rdi
0x140037f05  push    r12
0x140037f07  push    r14
0x140037f09  push    r15
0x140037f0b  sub     rsp, 50h
0x140037f0f  mov     rbp, rdx
0x140037f12  mov     r14, rcx
0x140037f15  lea     r8, aCvdsserviceCop_8; "CVdsService::CopyStorageDeviceIdDescrip"...
0x140037f1c  mov     edx, 5Eh ; '^'
0x140037f21  lea     rcx, [rsp+88h+var_48]
0x140037f26  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140037f2c  nop
0x140037f2d  test    r14, r14
0x140037f30  jz      loc_14003816A
0x140037f36  test    rbp, rbp
0x140037f39  jz      loc_14003816A
0x140037f3f  xor     edi, edi
0x140037f41  mov     r15d, [r14+8]
0x140037f45  mov     r8d, r15d
0x140037f48  lea     rdx, aCvdsserviceCop; "CVdsService::CopyStorageDeviceIdDescrip"...
0x140037f4f  lea     r12d, [rdi+2]
0x140037f53  mov     ecx, r12d
0x140037f56  call    cs:__imp_VdsTraceW
0x140037f5c  lea     rbx, [r14+0Ch]
0x140037f60  mov     rcx, rbx
0x140037f63  xor     edx, edx
0x140037f65  test    r15d, r15d
0x140037f68  jz      short loc_140037F84
0x140037f6a  lea     eax, [rdi+1]
0x140037f6d  cmp     dword ptr [rcx+0Ch], 0
0x140037f71  cmovnz  eax, edi
0x140037f74  mov     edi, eax
0x140037f76  movzx   eax, word ptr [rcx+0Ah]
0x140037f7a  add     rcx, rax
0x140037f7d  inc     edx
0x140037f7f  cmp     edx, r15d
0x140037f82  jb      short loc_140037F6A
0x140037f84  mov     eax, [r14]
0x140037f87  mov     [rbp+40h], eax
0x140037f8a  mov     r9d, 0Ch
0x140037f90  xor     esi, esi
0x140037f92  cmp     [r14+4], r9d
0x140037f96  jnb     short loc_140037FC7
0x140037f98  mov     [rbp+44h], esi
0x140037f9b  mov     eax, [r14]
0x140037f9e  mov     [rsp+88h+var_58], eax
0x140037fa2  mov     dword ptr [rsp+88h+var_60], edi
0x140037fa6  mov     eax, [r14+8]
0x140037faa  mov     dword ptr [rsp+88h+var_68], eax
0x140037fae  mov     r8d, [r14+4]
0x140037fb2  lea     rdx, aCvdsserviceCop_10; "CVdsService::CopyStorageDeviceIdDescrip"...
0x140037fb9  mov     ecx, r12d
0x140037fbc  call    cs:__imp_VdsTraceW
0x140037fc2  jmp     loc_140038182
0x140037fc7  mov     [rbp+44h], edi
0x140037fca  test    edi, edi
0x140037fcc  jnz     short loc_140037FE6
0x140037fce  xor     r8d, r8d
0x140037fd1  lea     rdx, aCvdsserviceCop_12; "CVdsService::CopyStorageDeviceIdDescrip"...
0x140037fd8  lea     ecx, [rdi+1]
0x140037fdb  call    cs:__imp_VdsTraceW
0x140037fe1  jmp     loc_140038182
0x140037fe6  mov     r8d, edi
0x140037fe9  lea     rdx, aCvdsserviceCop_7; "CVdsService::CopyStorageDeviceIdDescrip"...
0x140037ff0  mov     ecx, r12d
0x140037ff3  call    cs:__imp_VdsTraceW
0x140037ff9  mov     eax, edi
0x140037ffb  lea     rdi, [rax+rax*2]
0x140037fff  shl     rdi, 3
0x140038003  mov     rcx, rdi; cb
0x140038006  call    cs:__imp_CoTaskMemAlloc
0x14003800c  mov     [rbp+48h], rax
0x140038010  test    rax, rax
0x140038013  jnz     short loc_14003802A
0x140038015  mov     r8d, 8007000Eh
0x14003801b  mov     esi, r8d
0x14003801e  lea     rdx, aCvdsserviceCop_11; "CVdsService::CopyStorageDeviceIdDescrip"...
0x140038025  jmp     loc_140038179
0x14003802a  mov     r8, rdi; Size
0x14003802d  xor     edx, edx; Val
0x14003802f  mov     rcx, rax; void *
0x140038032  call    memset_0
0x140038037  mov     rdi, [rbp+48h]
0x14003803b  xor     ebp, ebp
0x14003803d  cmp     ebp, r15d
0x140038040  jnb     loc_140038182
0x140038046  cmp     [rbx+0Ch], esi
0x140038049  jz      short loc_140038056
0x14003804b  movzx   eax, word ptr [rbx+0Ah]
0x14003804f  add     rbx, rax
0x140038052  inc     ebp
0x140038054  jmp     short loc_14003803D
0x140038056  mov     eax, [rbx+4]
0x140038059  mov     [rdi+4], eax
0x14003805c  mov     eax, [rbx]
0x14003805e  mov     [rdi], eax
0x140038060  movzx   edx, word ptr [rbx+8]
0x140038064  xor     eax, eax
0x140038066  cmp     ax, dx
0x140038069  jnb     loc_140038136
0x14003806f  lea     r14d, [rbp+1]
0x140038073  cmp     r14d, r15d
0x140038076  jz      short loc_14003808A
0x140038078  mov     r9d, edx
0x14003807b  lea     ecx, [rdx+10h]
0x14003807e  movzx   eax, word ptr [rbx+0Ah]
0x140038082  cmp     ecx, eax
0x140038084  ja      loc_140038139
0x14003808a  mov     rcx, rdx; cb
0x14003808d  call    cs:__imp_CoTaskMemAlloc
0x140038093  mov     rcx, rax; void *
0x140038096  mov     [rdi+10h], rax
0x14003809a  test    rax, rax
0x14003809d  jz      loc_140038124
0x1400380a3  mov     ebp, r14d
0x1400380a6  movzx   eax, word ptr [rbx+8]
0x1400380aa  mov     [rdi+8], eax
0x1400380ad  movzx   r8d, word ptr [rbx+8]; Size
0x1400380b2  lea     rdx, [rbx+10h]; Src
0x1400380b6  call    memcpy_0
0x1400380bb  mov     eax, [rdi+8]
0x1400380be  mov     dword ptr [rsp+88h+var_60], eax
0x1400380c2  mov     eax, [rdi]
0x1400380c4  mov     dword ptr [rsp+88h+var_68], eax
0x1400380c8  mov     r9d, [rdi+4]
0x1400380cc  mov     r8d, [rbx+0Ch]
0x1400380d0  lea     rdx, aCvdsserviceCop_6; "CVdsService::CopyStorageDeviceIdDescrip"...
0x1400380d7  mov     ecx, r12d
0x1400380da  call    cs:__imp_VdsTraceW
0x1400380e0  mov     r14, [rdi+10h]
0x1400380e4  xor     r12d, r12d
0x1400380e7  cmp     [rdi+8], esi
0x1400380ea  jbe     short loc_14003810E
0x1400380ec  movzx   r8d, byte ptr [r14]
0x1400380f0  lea     rdx, aIdIdentifier2x; "ID identifier={%.2x}"
0x1400380f7  mov     ecx, 2
0x1400380fc  call    cs:__imp_VdsTraceW
0x140038102  inc     r14
0x140038105  inc     r12d
0x140038108  cmp     r12d, [rdi+8]
0x14003810c  jb      short loc_1400380EC
0x14003810e  movzx   eax, word ptr [rbx+0Ah]
0x140038112  add     rbx, rax
0x140038115  add     rdi, 18h
0x140038119  mov     r12d, 2
0x14003811f  jmp     loc_14003803D
0x140038124  mov     r8d, 8007000Eh
0x14003812a  mov     esi, r8d
0x14003812d  lea     rdx, aCvdsserviceCop_1; "CVdsService::CopyStorageDeviceIdDescrip"...
0x140038134  jmp     short loc_140038179
0x140038136  mov     r9d, edx
0x140038139  mov     esi, 8000FFFFh
0x14003813e  movzx   eax, word ptr [rbx+0Ah]
0x140038142  mov     [rsp+88h+var_50], esi
0x140038146  mov     [rsp+88h+var_58], r15d
0x14003814b  mov     dword ptr [rsp+88h+var_60], ebp
0x14003814f  mov     dword ptr [rsp+88h+var_68], eax
0x140038153  mov     r8d, 10h
0x140038159  lea     rdx, aCvdsserviceCop_9; "CVdsService::CopyStorageDeviceIdDescrip"...
0x140038160  xor     ecx, ecx
0x140038162  call    cs:__imp_VdsTraceW
0x140038168  jmp     short loc_140038182
0x14003816a  mov     esi, 80070057h
0x14003816f  mov     r8d, esi
0x140038172  lea     rdx, aCvdsserviceCop_3; "CVdsService::CopyStorageDeviceIdDescrip"...
0x140038179  xor     ecx, ecx
0x14003817b  call    cs:__imp_VdsTraceW
0x140038181  nop
0x140038182  lea     rcx, [rsp+88h+var_48]
0x140038187  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003818d  mov     eax, esi
0x14003818f  add     rsp, 50h
0x140038193  pop     r15
0x140038195  pop     r14
0x140038197  pop     r12
0x140038199  pop     rdi
0x14003819a  pop     rsi
0x14003819b  pop     rbp
0x14003819c  pop     rbx
0x14003819d  retn
```
