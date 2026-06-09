# BWCContentProviderConfiguration::CreateInstance(BWCContentProviderConfiguration * *)

- ea: `0x18000fac8`
- end: `0x18000fc26`
- name: `?CreateInstance@BWCContentProviderConfiguration@@SAJPEAPEAV1@@Z`
- size: `350`
- prototype: `__int64 __fastcall(struct BWCContentProviderConfiguration **, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e7f4`

## callees

- `0x180001074`
- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x18000fac8`
- `0x180010098`
- `0x180019010`

## string_xrefs

- `0x18000fafe`: `BWCContentProviderConfiguration::CreateInstance`
- `0x18000fb8c`: `BWCContentProviderConfiguration::CreateInstance`
- `0x18000fba3`: `BWCContentProviderConfiguration::CreateInstance`
- `0x18000fbc7`: `BWCContentProviderConfiguration::CreateInstance`
- `0x18000fbe5`: `BWCContentProviderConfiguration::CreateInstance`
- `0x18000faf1`: `BWCContentProviderConfig`

## pseudocode

```c
__int64 __fastcall BWCContentProviderConfiguration::CreateInstance(struct BWCContentProviderConfiguration **a1, int a2)
{
  unsigned int v3; // edi
  __int64 v4; // rcx
  BWCContentProviderConfiguration *v5; // rbx
  int v6; // eax
  __int64 v7; // rdx

  if ( !a1 )
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        0,
        a2,
        (unsigned int)"BWCContentProviderConfiguration::CreateInstance",
        -2147024809,
        (__int64)"BWCContentProviderConfig");
    return v3;
  }
  *a1 = 0;
  v5 = (BWCContentProviderConfiguration *)operator new(0x28u);
  if ( !v5 )
  {
    v3 = -2147024882;
    v5 = 0;
    goto LABEL_17;
  }
  *((_QWORD *)v5 + 1) = 0;
  *(_QWORD *)v5 = &BWCContentProviderConfiguration::`vftable';
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 4) = 0;
  v6 = BWCContentProviderConfiguration::Initialize(v5);
  v3 = v6;
  if ( v6 >= 0 )
  {
    *a1 = v5;
    goto LABEL_9;
  }
  if ( v6 == -2147024882 )
  {
LABEL_17:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    {
LABEL_20:
      if ( !v5 )
        return v3;
LABEL_21:
      (**(void (__fastcall ***)(BWCContentProviderConfiguration *, __int64))v5)(v5, 1);
      return v3;
    }
    McTemplateU0s_EventWriteTransfer(
      v4,
      SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY,
      "BWCContentProviderConfiguration::CreateInstance");
LABEL_19:
    if ( (v3 & 0x80000000) == 0 )
      return v3;
    goto LABEL_20;
  }
  if ( v6 == -2147024809 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v4, v7, "BWCContentProviderConfiguration::CreateInstance", 2147942487LL);
    goto LABEL_21;
  }
LABEL_9:
  if ( v6 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v4, v7, "BWCContentProviderConfiguration::CreateInstance", (unsigned int)v6);
    goto LABEL_19;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(
      v4,
      SDIAGPRV_EVENT_DEBUG_SUCCESS,
      "BWCContentProviderConfiguration::CreateInstance");
  return v3;
}

```

## disassembly

```asm
0x18000fac8  mov     [rsp+arg_0], rbx
0x18000facd  mov     [rsp+arg_8], rsi
0x18000fad2  push    rdi
0x18000fad3  sub     rsp, 30h
0x18000fad7  mov     rsi, rcx
0x18000fada  test    rcx, rcx
0x18000fadd  jnz     short loc_18000FB14
0x18000fadf  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fae6  mov     edi, 80070057h
0x18000faeb  jz      loc_18000FC14
0x18000faf1  lea     rax, aBwccontentprov_7; "BWCContentProviderConfig"
0x18000faf8  mov     r9d, 80070057h
0x18000fafe  lea     r8, aBwccontentprov_1; "BWCContentProviderConfiguration::Create"...
0x18000fb05  mov     [rsp+38h+var_18], rax
0x18000fb0a  call    McTemplateU0sqs_EventWriteTransfer
0x18000fb0f  jmp     loc_18000FC14
0x18000fb14  mov     qword ptr [rcx], 0
0x18000fb1b  mov     ecx, 28h ; '('; Size
0x18000fb20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fb25  mov     rbx, rax
0x18000fb28  test    rax, rax
0x18000fb2b  jz      loc_18000FBD5
0x18000fb31  lea     rax, ??_7BWCContentProviderConfiguration@@6B@; const BWCContentProviderConfiguration::`vftable'
0x18000fb38  mov     qword ptr [rbx+8], 0
0x18000fb40  mov     rcx, rbx; this
0x18000fb43  mov     [rbx], rax
0x18000fb46  mov     qword ptr [rbx+10h], 0
0x18000fb4e  mov     qword ptr [rbx+18h], 0
0x18000fb56  mov     qword ptr [rbx+20h], 0
0x18000fb5e  call    ?Initialize@BWCContentProviderConfiguration@@AEAAJXZ; BWCContentProviderConfiguration::Initialize(void)
0x18000fb63  mov     edi, eax
0x18000fb65  test    eax, eax
0x18000fb67  js      short loc_18000FB6E
0x18000fb69  mov     [rsi], rbx
0x18000fb6c  jmp     short loc_18000FB7C
0x18000fb6e  cmp     eax, 8007000Eh
0x18000fb73  jz      short loc_18000FBDC
0x18000fb75  cmp     eax, 80070057h
0x18000fb7a  jz      short loc_18000FBB8
0x18000fb7c  test    eax, eax
0x18000fb7e  jz      short loc_18000FB9A
0x18000fb80  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fb87  jz      short loc_18000FBF8
0x18000fb89  mov     r9d, eax
0x18000fb8c  lea     r8, aBwccontentprov_1; "BWCContentProviderConfiguration::Create"...
0x18000fb93  call    McTemplateU0sq_EventWriteTransfer
0x18000fb98  jmp     short loc_18000FBF8
0x18000fb9a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000fba1  jz      short loc_18000FC14
0x18000fba3  lea     r8, aBwccontentprov_1; "BWCContentProviderConfiguration::Create"...
0x18000fbaa  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000fbb1  call    McTemplateU0s_EventWriteTransfer
0x18000fbb6  jmp     short loc_18000FC14
0x18000fbb8  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fbbf  jz      short loc_18000FC01
0x18000fbc1  mov     r9d, 80070057h
0x18000fbc7  lea     r8, aBwccontentprov_1; "BWCContentProviderConfiguration::Create"...
0x18000fbce  call    McTemplateU0sq_EventWriteTransfer
0x18000fbd3  jmp     short loc_18000FC01
0x18000fbd5  mov     edi, 8007000Eh
0x18000fbda  xor     ebx, ebx
0x18000fbdc  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000fbe3  jz      short loc_18000FBFC
0x18000fbe5  lea     r8, aBwccontentprov_1; "BWCContentProviderConfiguration::Create"...
0x18000fbec  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000fbf3  call    McTemplateU0s_EventWriteTransfer
0x18000fbf8  test    edi, edi
0x18000fbfa  jns     short loc_18000FC14
0x18000fbfc  test    rbx, rbx
0x18000fbff  jz      short loc_18000FC14
0x18000fc01  mov     rax, [rbx]
0x18000fc04  mov     edx, 1
0x18000fc09  mov     rcx, rbx
0x18000fc0c  mov     rax, [rax]
0x18000fc0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc14  mov     rbx, [rsp+38h+arg_0]
0x18000fc19  mov     eax, edi
0x18000fc1b  mov     rsi, [rsp+38h+arg_8]
0x18000fc20  add     rsp, 30h
0x18000fc24  pop     rdi
0x18000fc25  retn
```
