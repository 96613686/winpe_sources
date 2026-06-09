# _DllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x18000202c`
- end: `0x180002173`
- name: `?_DllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `327`
- prototype: `__int64 __fastcall(HINSTANCE, int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000217c`

## callees

- `0x18000202c`
- `0x180002790`
- `0x1800028d0`
- `0x180003838`
- `0x180003b98`
- `0x180003e10`

## import_xrefs

- `ntdll!NtClose` at `0x180002120`
- `ntdll!NtClose` at `0x180002120`
- `ntdll!DbgPrintEx` at `0x18000208d`
- `ntdll!DbgPrintEx` at `0x1800020ad`
- `ntdll!DbgPrintEx` at `0x1800020d9`
- `ntdll!DbgPrintEx` at `0x18000210e`
- `ntdll!DbgPrintEx` at `0x18000214d`
- `ntdll!DbgPrintEx` at `0x18000208d`
- `ntdll!DbgPrintEx` at `0x1800020ad`
- `ntdll!DbgPrintEx` at `0x1800020d9`
- `ntdll!DbgPrintEx` at `0x18000210e`
- `ntdll!DbgPrintEx` at `0x18000214d`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180002039`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180002039`

## string_xrefs

- `0x180002086`: `WERDIAG: Verifier.dll loaded. Enabling Autoverifier.\n`
- `0x18000209f`: `WERDIAG: ProcessStartupSettingsUpdate failed. NTSTATUS: %08X\n`

## pseudocode

```c
__int64 __fastcall _DllMain(HINSTANCE a1, int a2, _QWORD *a3)
{
  int v3; // ecx
  int v4; // eax
  CAutoVerifierSettingsEngine *v5; // rcx
  int v6; // eax
  CFDRShim *v7; // rcx
  CFDRShim *v8; // rcx

  if ( a2 == 1 )
  {
    LdrDisableThreadCalloutsForDll(a1);
    v3 = g_bProcessAttachDone;
    if ( g_bProcessAttachDone )
    {
      v4 = g_bAppRecorderEnabled;
    }
    else
    {
      g_bAutoverifierEnabled = IsAutoverifierEnabled();
      v4 = IsAppRecorderEnabled();
      v3 = g_bProcessAttachDone;
      g_bAppRecorderEnabled = v4;
    }
    if ( g_bAutoverifierEnabled )
    {
      if ( !v3 )
      {
        DbgPrintEx(0x96u, 3u, "WERDIAG: Verifier.dll loaded. Enabling Autoverifier.\n");
        v6 = CAutoVerifierSettingsEngine::ProcessStartupSettingsUpdate(v5);
        if ( v6 < 0 )
          DbgPrintEx(0x96u, 0, "WERDIAG: ProcessStartupSettingsUpdate failed. NTSTATUS: %08X\n", v6);
        g_bProcessAttachDone = 1;
      }
    }
    else if ( !v4 )
    {
      DbgPrintEx(0x96u, 3u, "WERDIAG: FDR will be enabled\n");
      g_bAutoverifierEnabled = 0;
      CFDRShim::DeleteFDRLayer(v7);
    }
  }
  else if ( a2 )
  {
    if ( a2 == 4 )
      *a3 = &VfCoreProvider;
  }
  else if ( g_bAutoverifierEnabled == 1 )
  {
    DbgPrintEx(0x96u, 3u, "WERDIAG: Stopping Autoverifier\n");
    if ( Reserved7 )
    {
      NtClose(Reserved7);
      Reserved7 = 0;
    }
  }
  else if ( !g_bAppRecorderEnabled )
  {
    DbgPrintEx(0x96u, 3u, "WERDIAG: Stopping FDR\n");
    CFDRShim::CleanupSessionSettings(v8);
  }
  return 1;
}

```

## disassembly

```asm
0x18000202c  sub     rsp, 28h
0x180002030  cmp     edx, 1
0x180002033  jnz     loc_1800020F0
0x180002039  call    cs:__imp_LdrDisableThreadCalloutsForDll
0x18000203f  mov     ecx, cs:?g_bProcessAttachDone@@3HA; int g_bProcessAttachDone
0x180002045  test    ecx, ecx
0x180002047  jnz     short loc_180002067
0x180002049  call    ?IsAutoverifierEnabled@@YAHXZ; IsAutoverifierEnabled(void)
0x18000204e  mov     cs:?g_bAutoverifierEnabled@@3HA, eax; int g_bAutoverifierEnabled
0x180002054  call    ?IsAppRecorderEnabled@@YAHXZ; IsAppRecorderEnabled(void)
0x180002059  mov     ecx, cs:?g_bProcessAttachDone@@3HA; int g_bProcessAttachDone
0x18000205f  mov     cs:?g_bAppRecorderEnabled@@3HA, eax; int g_bAppRecorderEnabled
0x180002065  jmp     short loc_18000206D
0x180002067  mov     eax, cs:?g_bAppRecorderEnabled@@3HA; int g_bAppRecorderEnabled
0x18000206d  cmp     cs:?g_bAutoverifierEnabled@@3HA, 0; int g_bAutoverifierEnabled
0x180002074  jz      short loc_1800020C2
0x180002076  test    ecx, ecx
0x180002078  jnz     loc_180002169
0x18000207e  lea     edx, [rcx+3]; Level
0x180002081  mov     ecx, 96h; ComponentId
0x180002086  lea     r8, Format; "WERDIAG: Verifier.dll loaded. Enabling "...
0x18000208d  call    cs:__imp_DbgPrintEx
0x180002093  call    ?ProcessStartupSettingsUpdate@CAutoVerifierSettingsEngine@@QEAAJXZ; CAutoVerifierSettingsEngine::ProcessStartupSettingsUpdate(void)
0x180002098  test    eax, eax
0x18000209a  jns     short loc_1800020B3
0x18000209c  mov     r9d, eax
0x18000209f  lea     r8, aWerdiagProcess; "WERDIAG: ProcessStartupSettingsUpdate f"...
0x1800020a6  xor     edx, edx; Level
0x1800020a8  mov     ecx, 96h; ComponentId
0x1800020ad  call    cs:__imp_DbgPrintEx
0x1800020b3  mov     cs:?g_bProcessAttachDone@@3HA, 1; int g_bProcessAttachDone
0x1800020bd  jmp     loc_180002169
0x1800020c2  test    eax, eax
0x1800020c4  jnz     loc_180002169
0x1800020ca  lea     r8, aWerdiagFdrWill; "WERDIAG: FDR will be enabled\n"
0x1800020d1  mov     ecx, 96h; ComponentId
0x1800020d6  lea     edx, [rax+3]; Level
0x1800020d9  call    cs:__imp_DbgPrintEx
0x1800020df  mov     cs:?g_bAutoverifierEnabled@@3HA, 0; int g_bAutoverifierEnabled
0x1800020e9  call    ?DeleteFDRLayer@CFDRShim@@QEAAJXZ; CFDRShim::DeleteFDRLayer(void)
0x1800020ee  jmp     short loc_180002169
0x1800020f0  test    edx, edx
0x1800020f2  jnz     short loc_18000215A
0x1800020f4  cmp     cs:?g_bAutoverifierEnabled@@3HA, 1; int g_bAutoverifierEnabled
0x1800020fb  jnz     short loc_180002133
0x1800020fd  lea     r8, aWerdiagStoppin; "WERDIAG: Stopping Autoverifier\n"
0x180002104  mov     edx, 3; Level
0x180002109  mov     ecx, 96h; ComponentId
0x18000210e  call    cs:__imp_DbgPrintEx
0x180002114  mov     rcx, cs:Reserved7; Handle
0x18000211b  test    rcx, rcx
0x18000211e  jz      short loc_180002169
0x180002120  call    cs:__imp_NtClose
0x180002126  mov     cs:Reserved7, 0
0x180002131  jmp     short loc_180002169
0x180002133  cmp     cs:?g_bAppRecorderEnabled@@3HA, 0; int g_bAppRecorderEnabled
0x18000213a  jnz     short loc_180002169
0x18000213c  lea     r8, aWerdiagStoppin_0; "WERDIAG: Stopping FDR\n"
0x180002143  mov     edx, 3; Level
0x180002148  mov     ecx, 96h; ComponentId
0x18000214d  call    cs:__imp_DbgPrintEx
0x180002153  call    ?CleanupSessionSettings@CFDRShim@@QEAAJH@Z; CFDRShim::CleanupSessionSettings(int)
0x180002158  jmp     short loc_180002169
0x18000215a  cmp     edx, 4
0x18000215d  jnz     short loc_180002169
0x18000215f  lea     rcx, ?VfCoreProvider@@3U_RTL_VERIFIER_PROVIDER_DESCRIPTOR@@A; "P"
0x180002166  mov     [r8], rcx
0x180002169  mov     eax, 1
0x18000216e  add     rsp, 28h
0x180002172  retn
```
