# SDiagPrvSyncObject::InitSynch(void)

- ea: `0x180003540`
- end: `0x1800035c6`
- name: `?InitSynch@SDiagPrvSyncObject@@UEAAJXZ`
- size: `134`
- prototype: `__int64 __fastcall(SDiagPrvSyncObject *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004de0`
- `0x180007660`
- `0x180011480`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x180002f00`
- `0x180003540`

## pseudocode

```c
__int64 __fastcall SDiagPrvSyncObject::InitSynch(SDiagPrvSyncObject *this)
{
  int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  unsigned int v5; // ebx
  __int64 *v6; // rdx

  v2 = SDiagPrviInitializeCriticalSection((struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
  v5 = v2;
  if ( v2 < 0 )
  {
    if ( v2 == -2147024882 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        return v5;
      v6 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
      goto LABEL_11;
    }
  }
  else
  {
    *((_DWORD *)this + 2) = 1;
  }
  if ( !v2 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      return v5;
    v6 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_11:
    McTemplateU0s_EventWriteTransfer(v4, v6, "SDiagPrvSyncObject::InitSynch");
    return v5;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sq_EventWriteTransfer(v4, v3, "SDiagPrvSyncObject::InitSynch", (unsigned int)v2);
  return v5;
}

```

## disassembly

```asm
0x180003540  mov     [rsp+arg_0], rbx
0x180003545  push    rdi
0x180003546  sub     rsp, 20h
0x18000354a  mov     rdi, rcx
0x18000354d  add     rcx, 10h; struct _RTL_CRITICAL_SECTION *
0x180003551  call    ?SDiagPrviInitializeCriticalSection@@YAJPEAU_RTL_CRITICAL_SECTION@@@Z; SDiagPrviInitializeCriticalSection(_RTL_CRITICAL_SECTION *)
0x180003556  mov     ebx, eax
0x180003558  test    eax, eax
0x18000355a  js      short loc_180003565
0x18000355c  mov     dword ptr [rdi+8], 1
0x180003563  jmp     short loc_18000356D
0x180003565  cmp     ebx, 8007000Eh
0x18000356b  jz      short loc_18000359D
0x18000356d  test    ebx, ebx
0x18000356f  jz      short loc_18000358B
0x180003571  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180003578  jz      short loc_1800035B9
0x18000357a  mov     r9d, ebx
0x18000357d  lea     r8, aSdiagprvsyncob; "SDiagPrvSyncObject::InitSynch"
0x180003584  call    McTemplateU0sq_EventWriteTransfer
0x180003589  jmp     short loc_1800035B9
0x18000358b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180003592  jz      short loc_1800035B9
0x180003594  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000359b  jmp     short loc_1800035AD
0x18000359d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800035a4  jz      short loc_1800035B9
0x1800035a6  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x1800035ad  lea     r8, aSdiagprvsyncob; "SDiagPrvSyncObject::InitSynch"
0x1800035b4  call    McTemplateU0s_EventWriteTransfer
0x1800035b9  mov     eax, ebx
0x1800035bb  mov     rbx, [rsp+28h+arg_0]
0x1800035c0  add     rsp, 20h
0x1800035c4  pop     rdi
0x1800035c5  retn
```
