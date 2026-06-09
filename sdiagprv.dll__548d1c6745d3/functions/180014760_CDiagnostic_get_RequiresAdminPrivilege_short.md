# CDiagnostic::get_RequiresAdminPrivilege(short *)

- ea: `0x180014760`
- end: `0x180014832`
- name: `?get_RequiresAdminPrivilege@CDiagnostic@@UEAAJPEAF@Z`
- size: `210`
- prototype: `__int64 __fastcall(CDiagnostic *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800024d4`
- `0x1800025ec`
- `0x1800037fc`
- `0x180003908`
- `0x180003d30`
- `0x180014760`

## string_xrefs

- `0x180014779`: `CDiagnostic::get_RequiresAdminPrivilege`
- `0x18001479e`: `CDiagnostic::get_RequiresAdminPrivilege`
- `0x1800147ea`: `CDiagnostic::get_RequiresAdminPrivilege`
- `0x180014815`: `CDiagnostic::get_RequiresAdminPrivilege`
- `0x180014808`: `RequiresAdminPrivileges`

## pseudocode

```c
__int64 __fastcall CDiagnostic::get_RequiresAdminPrivilege(CDiagnostic *this, __int16 *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v6; // edx
  __int64 v7; // rcx

  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(
      this,
      SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START,
      "CDiagnostic::get_RequiresAdminPrivilege");
  SDiagPrvSyncObject::Lock((CDiagnostic *)((char *)this + 8));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(
      v4,
      SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END,
      "CDiagnostic::get_RequiresAdminPrivilege");
  if ( a2 )
  {
    v5 = 0;
    *a2 = *((_WORD *)this + 52);
  }
  else
  {
    v5 = -2147024809;
  }
  SDiagPrvSyncObject::Unlock((CDiagnostic *)((char *)this + 8));
  if ( v5 == -2147024809 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        v7,
        v6,
        (unsigned int)"CDiagnostic::get_RequiresAdminPrivilege",
        -2147024809,
        (__int64)"RequiresAdminPrivileges");
  }
  else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
  {
    McTemplateU0st_EventWriteTransfer(
      v7,
      SDIAGPRV_EVENT_DEBUG_GET_BOOL_SUCCESS,
      "CDiagnostic::get_RequiresAdminPrivilege",
      (unsigned int)*((__int16 *)this + 52));
  }
  return v5;
}

```

## disassembly

```asm
0x180014760  push    rbx
0x180014762  push    rsi
0x180014763  push    rdi
0x180014764  push    r14
0x180014766  sub     rsp, 38h
0x18001476a  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x180014771  mov     r14, rdx
0x180014774  mov     rdi, rcx
0x180014777  jge     short loc_18001478C
0x180014779  lea     r8, aCdiagnosticGet_9; "CDiagnostic::get_RequiresAdminPrivilege"
0x180014780  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x180014787  call    McTemplateU0s_EventWriteTransfer
0x18001478c  lea     rcx, [rdi+8]; this
0x180014790  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x180014795  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x18001479c  jge     short loc_1800147B1
0x18001479e  lea     r8, aCdiagnosticGet_9; "CDiagnostic::get_RequiresAdminPrivilege"
0x1800147a5  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x1800147ac  call    McTemplateU0s_EventWriteTransfer
0x1800147b1  test    r14, r14
0x1800147b4  jnz     short loc_1800147BD
0x1800147b6  mov     ebx, 80070057h
0x1800147bb  jmp     short loc_1800147C7
0x1800147bd  movzx   eax, word ptr [rdi+68h]
0x1800147c1  xor     ebx, ebx
0x1800147c3  mov     [r14], ax
0x1800147c7  lea     rcx, [rdi+8]; this
0x1800147cb  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x1800147d0  cmp     ebx, 80070057h
0x1800147d6  jz      short loc_1800147FF
0x1800147d8  test    ebx, ebx
0x1800147da  jnz     short loc_180014826
0x1800147dc  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800147e3  jz      short loc_180014826
0x1800147e5  movsx   r9d, word ptr [rdi+68h]
0x1800147ea  lea     r8, aCdiagnosticGet_9; "CDiagnostic::get_RequiresAdminPrivilege"
0x1800147f1  lea     rdx, SDIAGPRV_EVENT_DEBUG_GET_BOOL_SUCCESS
0x1800147f8  call    McTemplateU0st_EventWriteTransfer
0x1800147fd  jmp     short loc_180014826
0x1800147ff  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180014806  jz      short loc_180014826
0x180014808  lea     rax, aRequiresadminp; "RequiresAdminPrivileges"
0x18001480f  mov     r9d, 80070057h
0x180014815  lea     r8, aCdiagnosticGet_9; "CDiagnostic::get_RequiresAdminPrivilege"
0x18001481c  mov     [rsp+58h+var_38], rax
0x180014821  call    McTemplateU0sqs_EventWriteTransfer
0x180014826  mov     eax, ebx
0x180014828  add     rsp, 38h
0x18001482c  pop     r14
0x18001482e  pop     rdi
0x18001482f  pop     rsi
0x180014830  pop     rbx
0x180014831  retn
```
