# ATL::IServiceProviderImpl<CWMPRichPreviewRemoteService>::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x140007750`
- end: `0x1400077b3`
- name: `?QueryService@?$IServiceProviderImpl@VCWMPRichPreviewRemoteService@@@ATL@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140007750`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::IServiceProviderImpl<CWMPRichPreviewRemoteService>::QueryService(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 (__fastcall ***v5)(_QWORD, __int64, _QWORD *); // rcx

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v5 = (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD *))((a1 - 8) & -(__int64)(a1 != 0));
  if ( *a2 == -550292365
    && a2[1] == *(_DWORD *)&GUID_df333473_2cf7_4be2_907f_9aad5661364f.Data2
    && a2[2] == *(_DWORD *)GUID_df333473_2cf7_4be2_907f_9aad5661364f.Data4
    && a2[3] == *(_DWORD *)&GUID_df333473_2cf7_4be2_907f_9aad5661364f.Data4[4] )
  {
    return (**v5)(v5, a3, a4);
  }
  else
  {
    return 2147500034LL;
  }
}

```

## disassembly

```asm
0x140007750  mov     r10, r8
0x140007753  test    r9, r9
0x140007756  jnz     short loc_14000775F
0x140007758  mov     eax, 80004003h
0x14000775d  jmp     short locret_1400077B2
0x14000775f  lea     rax, [rcx-8]
0x140007763  mov     qword ptr [r9], 0
0x14000776a  neg     rcx
0x14000776d  sbb     rcx, rcx
0x140007770  and     rcx, rax
0x140007773  cmp     dword ptr [rdx], 0DF333473h
0x140007779  jnz     short loc_1400077AD
0x14000777b  mov     eax, dword ptr cs:_GUID_df333473_2cf7_4be2_907f_9aad5661364f.Data2
0x140007781  cmp     [rdx+4], eax
0x140007784  jnz     short loc_1400077AD
0x140007786  mov     eax, dword ptr cs:_GUID_df333473_2cf7_4be2_907f_9aad5661364f.Data4
0x14000778c  cmp     [rdx+8], eax
0x14000778f  jnz     short loc_1400077AD
0x140007791  mov     eax, dword ptr cs:_GUID_df333473_2cf7_4be2_907f_9aad5661364f.Data4+4
0x140007797  cmp     [rdx+0Ch], eax
0x14000779a  jnz     short loc_1400077AD
0x14000779c  mov     rax, [rcx]
0x14000779f  mov     r8, r9
0x1400077a2  mov     rdx, r10
0x1400077a5  mov     rax, [rax]
0x1400077a8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1400077ad  mov     eax, 80004002h
0x1400077b2  retn
```
