# DestroySystemConfiguration(_SYSTEM_CONFIGURATION *)

- ea: `0x18001555c`
- end: `0x1800156be`
- name: `?DestroySystemConfiguration@@YAJPEAU_SYSTEM_CONFIGURATION@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(struct _SYSTEM_CONFIGURATION *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009a8c`
- `0x180015ae8`

## callees

- `0x1800024d4`
- `0x1800025ec`
- `0x18001555c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800155b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180015601`
- `OLEAUT32!__imp_SysFreeString` at `0x180015614`
- `OLEAUT32!__imp_SysFreeString` at `0x180015627`
- `OLEAUT32!__imp_SysFreeString` at `0x18001563a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001564d`
- `OLEAUT32!__imp_SysFreeString` at `0x180015660`
- `OLEAUT32!__imp_SysFreeString` at `0x180015673`
- `OLEAUT32!__imp_SysFreeString` at `0x180015686`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155ee`
- `OLEAUT32!__imp_SysFreeString` at `0x180015601`
- `OLEAUT32!__imp_SysFreeString` at `0x180015614`
- `OLEAUT32!__imp_SysFreeString` at `0x180015627`
- `OLEAUT32!__imp_SysFreeString` at `0x18001563a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001564d`
- `OLEAUT32!__imp_SysFreeString` at `0x180015660`
- `OLEAUT32!__imp_SysFreeString` at `0x180015673`
- `OLEAUT32!__imp_SysFreeString` at `0x180015686`

## string_xrefs

- `0x180015587`: `SystemConfiguration`
- `0x180015594`: `DestroySystemConfiguration`
- `0x180015699`: `DestroySystemConfiguration`

## pseudocode

```c
__int64 __fastcall DestroySystemConfiguration(struct _SYSTEM_CONFIGURATION *a1, int a2)
{
  unsigned int v3; // edi
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx
  OLECHAR *v6; // rcx
  OLECHAR *v7; // rcx
  OLECHAR *v8; // rcx
  OLECHAR *v9; // rcx
  OLECHAR *v10; // rcx
  OLECHAR *v11; // rcx
  OLECHAR *v12; // rcx
  OLECHAR *v13; // rcx
  OLECHAR *v14; // rcx
  OLECHAR *v15; // rcx

  if ( a1 )
  {
    v4 = (OLECHAR *)*((_QWORD *)a1 + 3);
    v3 = 0;
    if ( v4 )
    {
      SysFreeString(v4);
      *((_QWORD *)a1 + 3) = 0;
    }
    v5 = (OLECHAR *)*((_QWORD *)a1 + 5);
    if ( v5 )
    {
      SysFreeString(v5);
      *((_QWORD *)a1 + 5) = 0;
    }
    v6 = (OLECHAR *)*((_QWORD *)a1 + 6);
    if ( v6 )
    {
      SysFreeString(v6);
      *((_QWORD *)a1 + 6) = 0;
    }
    v7 = (OLECHAR *)*((_QWORD *)a1 + 7);
    if ( v7 )
    {
      SysFreeString(v7);
      *((_QWORD *)a1 + 7) = 0;
    }
    v8 = (OLECHAR *)*((_QWORD *)a1 + 8);
    if ( v8 )
    {
      SysFreeString(v8);
      *((_QWORD *)a1 + 8) = 0;
    }
    v9 = (OLECHAR *)*((_QWORD *)a1 + 9);
    if ( v9 )
    {
      SysFreeString(v9);
      *((_QWORD *)a1 + 9) = 0;
    }
    v10 = (OLECHAR *)*((_QWORD *)a1 + 10);
    if ( v10 )
    {
      SysFreeString(v10);
      *((_QWORD *)a1 + 10) = 0;
    }
    v11 = (OLECHAR *)*((_QWORD *)a1 + 11);
    if ( v11 )
    {
      SysFreeString(v11);
      *((_QWORD *)a1 + 11) = 0;
    }
    v12 = (OLECHAR *)*((_QWORD *)a1 + 12);
    if ( v12 )
    {
      SysFreeString(v12);
      *((_QWORD *)a1 + 12) = 0;
    }
    v13 = (OLECHAR *)*((_QWORD *)a1 + 13);
    if ( v13 )
    {
      SysFreeString(v13);
      *((_QWORD *)a1 + 13) = 0;
    }
    v14 = (OLECHAR *)*((_QWORD *)a1 + 14);
    if ( v14 )
    {
      SysFreeString(v14);
      *((_QWORD *)a1 + 14) = 0;
    }
    v15 = (OLECHAR *)*((_QWORD *)a1 + 15);
    if ( v15 )
    {
      SysFreeString(v15);
      *((_QWORD *)a1 + 15) = 0;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      McTemplateU0s_EventWriteTransfer(v15, SDIAGPRV_EVENT_DEBUG_SUCCESS, "DestroySystemConfiguration");
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        0,
        a2,
        (unsigned int)"DestroySystemConfiguration",
        -2147024809,
        (__int64)"SystemConfiguration");
  }
  return v3;
}

```

## disassembly

```asm
0x18001555c  mov     [rsp+arg_0], rbx
0x180015561  mov     [rsp+arg_8], rsi
0x180015566  push    rdi
0x180015567  sub     rsp, 30h
0x18001556b  xor     esi, esi
0x18001556d  mov     rbx, rcx
0x180015570  test    rcx, rcx
0x180015573  jnz     short loc_1800155AA
0x180015575  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001557c  mov     edi, 80070057h
0x180015581  jz      loc_1800156AC
0x180015587  lea     rax, aSystemconfigur; "SystemConfiguration"
0x18001558e  mov     r9d, 80070057h
0x180015594  lea     r8, aDestroysystemc; "DestroySystemConfiguration"
0x18001559b  mov     [rsp+38h+var_18], rax
0x1800155a0  call    McTemplateU0sqs_EventWriteTransfer
0x1800155a5  jmp     loc_1800156AC
0x1800155aa  mov     rcx, [rcx+18h]; bstrString
0x1800155ae  mov     edi, esi
0x1800155b0  test    rcx, rcx
0x1800155b3  jz      short loc_1800155BF
0x1800155b5  call    cs:__imp_SysFreeString
0x1800155bb  mov     [rbx+18h], rsi
0x1800155bf  mov     rcx, [rbx+28h]; bstrString
0x1800155c3  test    rcx, rcx
0x1800155c6  jz      short loc_1800155D2
0x1800155c8  call    cs:__imp_SysFreeString
0x1800155ce  mov     [rbx+28h], rsi
0x1800155d2  mov     rcx, [rbx+30h]; bstrString
0x1800155d6  test    rcx, rcx
0x1800155d9  jz      short loc_1800155E5
0x1800155db  call    cs:__imp_SysFreeString
0x1800155e1  mov     [rbx+30h], rsi
0x1800155e5  mov     rcx, [rbx+38h]; bstrString
0x1800155e9  test    rcx, rcx
0x1800155ec  jz      short loc_1800155F8
0x1800155ee  call    cs:__imp_SysFreeString
0x1800155f4  mov     [rbx+38h], rsi
0x1800155f8  mov     rcx, [rbx+40h]; bstrString
0x1800155fc  test    rcx, rcx
0x1800155ff  jz      short loc_18001560B
0x180015601  call    cs:__imp_SysFreeString
0x180015607  mov     [rbx+40h], rsi
0x18001560b  mov     rcx, [rbx+48h]; bstrString
0x18001560f  test    rcx, rcx
0x180015612  jz      short loc_18001561E
0x180015614  call    cs:__imp_SysFreeString
0x18001561a  mov     [rbx+48h], rsi
0x18001561e  mov     rcx, [rbx+50h]; bstrString
0x180015622  test    rcx, rcx
0x180015625  jz      short loc_180015631
0x180015627  call    cs:__imp_SysFreeString
0x18001562d  mov     [rbx+50h], rsi
0x180015631  mov     rcx, [rbx+58h]; bstrString
0x180015635  test    rcx, rcx
0x180015638  jz      short loc_180015644
0x18001563a  call    cs:__imp_SysFreeString
0x180015640  mov     [rbx+58h], rsi
0x180015644  mov     rcx, [rbx+60h]; bstrString
0x180015648  test    rcx, rcx
0x18001564b  jz      short loc_180015657
0x18001564d  call    cs:__imp_SysFreeString
0x180015653  mov     [rbx+60h], rsi
0x180015657  mov     rcx, [rbx+68h]; bstrString
0x18001565b  test    rcx, rcx
0x18001565e  jz      short loc_18001566A
0x180015660  call    cs:__imp_SysFreeString
0x180015666  mov     [rbx+68h], rsi
0x18001566a  mov     rcx, [rbx+70h]; bstrString
0x18001566e  test    rcx, rcx
0x180015671  jz      short loc_18001567D
0x180015673  call    cs:__imp_SysFreeString
0x180015679  mov     [rbx+70h], rsi
0x18001567d  mov     rcx, [rbx+78h]; bstrString
0x180015681  test    rcx, rcx
0x180015684  jz      short loc_180015690
0x180015686  call    cs:__imp_SysFreeString
0x18001568c  mov     [rbx+78h], rsi
0x180015690  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180015697  jz      short loc_1800156AC
0x180015699  lea     r8, aDestroysystemc; "DestroySystemConfiguration"
0x1800156a0  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800156a7  call    McTemplateU0s_EventWriteTransfer
0x1800156ac  mov     rbx, [rsp+38h+arg_0]
0x1800156b1  mov     eax, edi
0x1800156b3  mov     rsi, [rsp+38h+arg_8]
0x1800156b8  add     rsp, 30h
0x1800156bc  pop     rdi
0x1800156bd  retn
```
