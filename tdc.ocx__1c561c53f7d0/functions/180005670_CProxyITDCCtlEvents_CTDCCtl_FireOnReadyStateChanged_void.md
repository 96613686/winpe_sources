# CProxyITDCCtlEvents<CTDCCtl>::FireOnReadyStateChanged(void)

- ea: `0x180005670`
- end: `0x180005712`
- name: `?FireOnReadyStateChanged@?$CProxyITDCCtlEvents@VCTDCCtl@@@@QEAAXXZ`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800097d4`
- `0x18000ea80`

## callees

- `0x180005670`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CProxyITDCCtlEvents<CTDCCtl>::FireOnReadyStateChanged(__int64 a1)
{
  __int64 *v1; // rbx
  __int64 result; // rax
  __int64 v4; // rcx
  int v5; // [rsp+20h] [rbp-58h]
  __int128 v6; // [rsp+50h] [rbp-28h] BYREF
  __int64 v7; // [rsp+60h] [rbp-18h]

  v1 = *(__int64 **)(a1 + 8);
  result = *(int *)(a1 + 16);
  if ( v1 < &v1[result] )
  {
    do
    {
      v4 = *v1;
      if ( *v1 )
      {
        v7 = 0;
        v6 = 0;
        LOWORD(v5) = 1;
        (*(void (__fastcall **)(__int64, __int64, GUID *, _QWORD, int, __int128 *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v4 + 48LL))(
          v4,
          4294966687LL,
          &GUID_NULL,
          0,
          v5,
          &v6,
          0,
          0,
          0);
      }
      ++v1;
      result = *(_QWORD *)(a1 + 8);
    }
    while ( (unsigned __int64)v1 < result + 8LL * *(int *)(a1 + 16) );
  }
  return result;
}

```

## disassembly

```asm
0x180005670  mov     [rsp+arg_0], rbx
0x180005675  push    rdi
0x180005676  sub     rsp, 70h
0x18000567a  mov     rbx, [rcx+8]
0x18000567e  mov     rdi, rcx
0x180005681  movsxd  rax, dword ptr [rcx+10h]
0x180005685  lea     rdx, [rbx+rax*8]
0x180005689  cmp     rbx, rdx
0x18000568c  jnb     short loc_180005704
0x18000568e  mov     rcx, [rbx]
0x180005691  test    rcx, rcx
0x180005694  jz      short loc_1800056EF
0x180005696  mov     [rsp+78h+var_38], 0
0x18000569f  lea     rdx, [rsp+78h+var_28]
0x1800056a4  mov     [rsp+78h+var_40], 0
0x1800056ad  lea     r8, GUID_NULL
0x1800056b4  xorps   xmm0, xmm0
0x1800056b7  mov     [rsp+78h+var_18], 0
0x1800056c0  movdqu  [rsp+78h+var_28], xmm0
0x1800056c6  mov     rax, [rcx]
0x1800056c9  xor     r9d, r9d
0x1800056cc  mov     [rsp+78h+var_48], 0
0x1800056d5  mov     [rsp+78h+var_50], rdx
0x1800056da  mov     edx, 0FFFFFD9Fh
0x1800056df  mov     [rsp+78h+var_58], 1
0x1800056e6  mov     rax, [rax+30h]
0x1800056ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ef  movsxd  rcx, dword ptr [rdi+10h]
0x1800056f3  add     rbx, 8
0x1800056f7  mov     rax, [rdi+8]
0x1800056fb  lea     rcx, [rax+rcx*8]
0x1800056ff  cmp     rbx, rcx
0x180005702  jb      short loc_18000568E
0x180005704  mov     rbx, [rsp+78h+arg_0]
0x18000570c  add     rsp, 70h
0x180005710  pop     rdi
0x180005711  retn
```
