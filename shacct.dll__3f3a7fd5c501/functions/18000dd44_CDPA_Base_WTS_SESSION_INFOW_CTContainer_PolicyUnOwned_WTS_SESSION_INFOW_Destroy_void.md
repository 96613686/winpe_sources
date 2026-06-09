# CDPA_Base<_WTS_SESSION_INFOW,CTContainer_PolicyUnOwned<_WTS_SESSION_INFOW>>::Destroy(void)

- ea: `0x18000dd44`
- end: `0x18000dd86`
- name: `?Destroy@?$CDPA_Base@U_WTS_SESSION_INFOW@@V?$CTContainer_PolicyUnOwned@U_WTS_SESSION_INFOW@@@@@@QEAAHXZ`
- size: `66`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008640`
- `0x18000d978`
- `0x18000d9f8`
- `0x1800142a0`

## callees

- `0x180009a50`
- `0x18000bbd0`
- `0x18000dd44`

## pseudocode

```c
BOOL __fastcall CDPA_Base<_WTS_SESSION_INFOW,CTContainer_PolicyUnOwned<_WTS_SESSION_INFOW>>::Destroy(struct _DPA **a1)
{
  BOOL result; // eax
  struct _DPA *v3; // rcx

  result = 1;
  v3 = *a1;
  if ( v3 )
  {
    g_pfn_DPA_DestroyCallback(
      v3,
      (PFNDAENUMCALLBACK)CDPA_Base<_SID,CTContainer_PolicyUnOwned<_SID>>::_StandardDestroyCB,
      0);
    *a1 = 0;
    result = DPA_Destroy(0);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000dd44  push    rbx
0x18000dd46  sub     rsp, 20h
0x18000dd4a  mov     rbx, rcx
0x18000dd4d  mov     eax, 1
0x18000dd52  mov     rcx, [rcx]; hdpa
0x18000dd55  test    rcx, rcx
0x18000dd58  jz      short loc_18000DD80
0x18000dd5a  xor     r8d, r8d; pData
0x18000dd5d  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@U_SID@@V?$CTContainer_PolicyUnOwned@U_SID@@@@@@CAHPEAU_SID@@PEAX@Z; pfnCB
0x18000dd64  call    cs:g_pfn_DPA_DestroyCallback
0x18000dd6a  xor     ecx, ecx; hdpa
0x18000dd6c  mov     qword ptr [rbx], 0
0x18000dd73  call    cs:__imp_DPA_Destroy
0x18000dd79  mov     qword ptr [rbx], 0
0x18000dd80  add     rsp, 20h
0x18000dd84  pop     rbx
0x18000dd85  retn
```
