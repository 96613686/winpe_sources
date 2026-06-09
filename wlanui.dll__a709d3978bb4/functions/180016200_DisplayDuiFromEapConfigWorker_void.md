# DisplayDuiFromEapConfigWorker(void *)

- ea: `0x180016200`
- end: `0x180016239`
- name: `?DisplayDuiFromEapConfigWorker@@YAIPEAX@Z`
- size: `57`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800160f0`

## import_xrefs

- `msvcrt!_endthreadex` at `0x18001622b`
- `msvcrt!_endthreadex` at `0x18001622b`

## pseudocode

```c
__int64 __fastcall DisplayDuiFromEapConfigWorker(void *a1)
{
  *(_DWORD *)a1 = DisplayDuiFromEapConfigInternal(
                    *((HWND *)a1 + 1),
                    *((HINSTANCE *)a1 + 2),
                    *((struct _CREDS_DLG_PARAMETERS **)a1 + 3),
                    *((_DWORD *)a1 + 8),
                    *((struct _PLAP_INPUT_FIELD_DATA **)a1 + 5));
  _endthreadex(0);
  return 0;
}

```

## disassembly

```asm
0x180016200  push    rbx
0x180016202  sub     rsp, 30h
0x180016206  mov     rax, [rcx+28h]
0x18001620a  mov     rbx, rcx
0x18001620d  mov     r9d, [rcx+20h]; unsigned int
0x180016211  mov     r8, [rcx+18h]; struct _CREDS_DLG_PARAMETERS *
0x180016215  mov     rdx, [rcx+10h]; HINSTANCE
0x180016219  mov     rcx, [rcx+8]; HWND
0x18001621d  mov     [rsp+38h+var_18], rax; struct _PLAP_INPUT_FIELD_DATA *
0x180016222  call    ?DisplayDuiFromEapConfigInternal@@YAKPEAUHWND__@@PEAUHINSTANCE__@@PEAU_CREDS_DLG_PARAMETERS@@KPEAU_PLAP_INPUT_FIELD_DATA@@@Z; DisplayDuiFromEapConfigInternal(HWND__ *,HINSTANCE__ *,_CREDS_DLG_PARAMETERS *,ulong,_PLAP_INPUT_FIELD_DATA *)
0x180016227  xor     ecx, ecx; ReturnCode
0x180016229  mov     [rbx], eax
0x18001622b  call    cs:__imp__endthreadex
0x180016231  xor     eax, eax
0x180016233  add     rsp, 30h
0x180016237  pop     rbx
0x180016238  retn
```
