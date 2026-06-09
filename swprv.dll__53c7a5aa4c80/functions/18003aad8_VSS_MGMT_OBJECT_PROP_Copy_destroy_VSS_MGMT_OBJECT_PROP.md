# VSS_MGMT_OBJECT_PROP_Copy::destroy(_VSS_MGMT_OBJECT_PROP *)

- ea: `0x18003aad8`
- end: `0x18003abbc`
- name: `?destroy@VSS_MGMT_OBJECT_PROP_Copy@@SAXPEAU_VSS_MGMT_OBJECT_PROP@@@Z`
- size: `228`
- prototype: `void __fastcall(struct _VSS_MGMT_OBJECT_PROP *)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180025ea4`
- `0x180026650`
- `0x18003ae94`
- `0x18003b0ec`
- `0x18003b5e8`

## callees

- `0x18000212c`
- `0x180033a8c`
- `0x180033c78`
- `0x18003aad8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ab7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ab8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ab7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ab8d`

## string_xrefs

- `0x18003ab02`: `PRPCOPYC`
- `0x18003aae6`: `base\stor\vss\modules\prop\copy.cxx`
- `0x18003aaf4`: `VSS_MGMT_OBJECT_PROP_Copy::destroy`

## pseudocode

```c
void __fastcall VSS_MGMT_OBJECT_PROP_Copy::destroy(struct _VSS_MGMT_OBJECT_PROP *a1)
{
  LPVOID v2[14]; // [rsp+60h] [rbp-128h] BYREF
  _QWORD v3[3]; // [rsp+D0h] [rbp-B8h] BYREF
  int v4; // [rsp+E8h] [rbp-A0h]
  int v5; // [rsp+ECh] [rbp-9Ch]
  int v6; // [rsp+F0h] [rbp-98h]
  _DWORD v7[36]; // [rsp+F8h] [rbp-90h] BYREF

  v3[0] = L"base\\stor\\vss\\modules\\prop\\copy.cxx";
  v3[1] = L"VSS_MGMT_OBJECT_PROP_Copy::destroy";
  v3[2] = L"PRPCOPYC";
  v4 = 351;
  v5 = 11;
  v6 = 255;
  v7[30] = 0x1000000;
  memset_0(v7, 0, 0x78u);
  CVssFunctionTracer::CVssFunctionTracer((__int64)v2, (__int64)v3, 0);
  if ( a1 )
  {
    if ( a1->Type == VSS_MGMT_OBJECT_VOLUME || (unsigned int)(a1->Type - 2) <= 1 )
    {
      CoTaskMemFree(a1->Obj.Vol.m_pwszVolumeName);
      a1->Obj.Vol.m_pwszVolumeName = 0;
      CoTaskMemFree(a1->Obj.Vol.m_pwszVolumeDisplayName);
      a1->Obj.Vol.m_pwszVolumeDisplayName = 0;
    }
    a1->Type = VSS_MGMT_OBJECT_UNKNOWN;
  }
  CVssFunctionTracer::~CVssFunctionTracer(v2);
}

```

## disassembly

```asm
0x18003aad8  mov     r11, rsp
0x18003aadb  push    rbx
0x18003aadc  sub     rsp, 180h
0x18003aae3  mov     rbx, rcx
0x18003aae6  lea     rax, aBaseStorVssMod_17; "base\\stor\\vss\\modules\\prop\\copy.cx"...
0x18003aaed  mov     [r11-0B8h], rax
0x18003aaf4  lea     rax, aVssMgmtObjectP_4; "VSS_MGMT_OBJECT_PROP_Copy::destroy"
0x18003aafb  mov     [r11-0B0h], rax
0x18003ab02  lea     rax, aPrpcopyc; "PRPCOPYC"
0x18003ab09  mov     [r11-0A8h], rax
0x18003ab10  mov     [rsp+188h+var_A0], 15Fh
0x18003ab1b  mov     [rsp+188h+var_9C], 0Bh
0x18003ab26  mov     [rsp+188h+var_98], 0FFh
0x18003ab31  mov     dword ptr [r11-18h], 1000000h
0x18003ab39  xor     edx, edx; Val
0x18003ab3b  lea     r8d, [rdx+78h]; Size
0x18003ab3f  lea     rcx, [r11-90h]; void *
0x18003ab46  call    memset_0
0x18003ab4b  xor     r8d, r8d
0x18003ab4e  lea     rdx, [rsp+188h+var_B8]
0x18003ab56  lea     rcx, [rsp+188h+var_128]
0x18003ab5b  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003ab60  nop
0x18003ab61  test    rbx, rbx
0x18003ab64  jz      short loc_18003ABA1
0x18003ab66  mov     ecx, [rbx]
0x18003ab68  sub     ecx, 1
0x18003ab6b  jz      short loc_18003AB77
0x18003ab6d  sub     ecx, 1
0x18003ab70  jz      short loc_18003AB77
0x18003ab72  cmp     ecx, 1
0x18003ab75  jnz     short loc_18003AB9B
0x18003ab77  mov     rcx, [rbx+8]; pv
0x18003ab7b  call    cs:__imp_CoTaskMemFree
0x18003ab81  mov     qword ptr [rbx+8], 0
0x18003ab89  mov     rcx, [rbx+10h]; pv
0x18003ab8d  call    cs:__imp_CoTaskMemFree
0x18003ab93  mov     qword ptr [rbx+10h], 0
0x18003ab9b  mov     dword ptr [rbx], 0
0x18003aba1  jmp     short loc_18003ABA9
0x18003aba3  jmp     short loc_18003ABA9
0x18003aba5  jmp     short loc_18003ABA9
0x18003aba7  jmp     short $+2
0x18003aba9  lea     rcx, [rsp+188h+var_128]; this
0x18003abae  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003abb3  add     rsp, 180h
0x18003abba  pop     rbx
0x18003abbb  retn
```
