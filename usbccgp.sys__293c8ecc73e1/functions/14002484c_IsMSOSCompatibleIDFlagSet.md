# IsMSOSCompatibleIDFlagSet

- ea: `0x14002484c`
- end: `0x14002491f`
- name: `IsMSOSCompatibleIDFlagSet`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400249d4`

## callees

- `0x14000a6cc`
- `0x14002484c`
- `0x14002e100`

## pseudocode

```c
char __fastcall IsMSOSCompatibleIDFlagSet(__int64 a1)
{
  __int64 v2; // rcx
  char v3; // bl
  int PdoRegistryParameter; // eax
  int v5; // edx
  char v6; // cl
  int v7; // r9d
  int v8; // r8d
  ULONG v10; // [rsp+30h] [rbp-18h]
  int v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+58h] [rbp+10h] BYREF

  LOBYTE(v10) = 1;
  v2 = *(_QWORD *)(a1 + 232);
  v11 = 0;
  v12 = 0;
  v3 = 0;
  PdoRegistryParameter = GetPdoRegistryParameter(
                           *(struct _DEVICE_OBJECT **)(v2 + 24),
                           L"EnumeratorFlag",
                           &v12,
                           4u,
                           &v11,
                           0,
                           v10);
  v6 = PdoRegistryParameter;
  if ( PdoRegistryParameter >= 0 )
  {
    v6 = v11;
    if ( v11 == 4 )
    {
      return v12 & 1;
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = 71;
      LOBYTE(v5) = 2;
      v8 = 8;
      goto LABEL_8;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v7 = 70;
    v8 = 2;
    LOBYTE(v5) = 2;
LABEL_8:
    WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 392), v5, v8, v7, (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids, v6);
  }
  return v3;
}

```

## disassembly

```asm
0x14002484c  mov     rax, rsp
0x14002484f  mov     [rax+18h], rbx
0x140024853  push    rdi
0x140024854  sub     rsp, 40h
0x140024858  mov     byte ptr [rax-18h], 1
0x14002485c  mov     rdi, rcx
0x14002485f  mov     rcx, [rcx+0E8h]
0x140024866  mov     r9d, 4
0x14002486c  mov     qword ptr [rax-20h], 0
0x140024874  lea     r8, [rsp+48h+arg_8]
0x140024879  mov     dword ptr [rax+8], 0
0x140024880  lea     rdx, aEnumeratorflag; "EnumeratorFlag"
0x140024887  mov     dword ptr [rax+10h], 0
0x14002488e  lea     rax, [rax+8]
0x140024892  mov     rcx, [rcx+18h]
0x140024896  xor     bl, bl
0x140024898  mov     [rsp+48h+var_28], rax
0x14002489d  call    GetPdoRegistryParameter
0x1400248a2  mov     ecx, eax
0x1400248a4  test    eax, eax
0x1400248a6  jns     short loc_1400248C7
0x1400248a8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400248af  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400248b6  jz      short loc_140024911
0x1400248b8  mov     r9d, 46h ; 'F'
0x1400248be  lea     r8d, [r9-44h]
0x1400248c2  mov     dl, r8b
0x1400248c5  jmp     short loc_1400248F5
0x1400248c7  mov     ecx, [rsp+48h+arg_0]
0x1400248cb  cmp     ecx, 4
0x1400248ce  jnz     short loc_1400248D9
0x1400248d0  mov     bl, byte ptr [rsp+48h+arg_8]
0x1400248d4  and     bl, 1
0x1400248d7  jmp     short loc_140024911
0x1400248d9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400248e0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400248e7  jz      short loc_140024911
0x1400248e9  mov     r9d, 47h ; 'G'
0x1400248ef  mov     dl, 2
0x1400248f1  lea     r8d, [r9-3Fh]
0x1400248f5  mov     [rsp+48h+var_20], ecx
0x1400248f9  lea     rax, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x140024900  mov     rcx, [rdi+188h]
0x140024907  mov     [rsp+48h+var_28], rax
0x14002490c  call    WPP_RECORDER_SF_d
0x140024911  mov     al, bl
0x140024913  mov     rbx, [rsp+48h+arg_10]
0x140024918  add     rsp, 40h
0x14002491c  pop     rdi
0x14002491d  retn
```
