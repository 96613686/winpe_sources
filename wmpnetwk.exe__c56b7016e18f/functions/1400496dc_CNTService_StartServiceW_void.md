# CNTService::StartServiceW(void)

- ea: `0x1400496dc`
- end: `0x140049892`
- name: `?StartServiceW@CNTService@@QEAAKXZ`
- size: `438`
- prototype: `unsigned int __fastcall(CNTService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x1400479b0`

## callees

- `0x14003f17c`
- `0x140047798`
- `0x1400496dc`

## import_xrefs

- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x14004980a`
- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x14004980a`
- `KERNEL32!CreateEventW` at `0x140049746`
- `KERNEL32!CreateEventW` at `0x140049793`
- `KERNEL32!CreateEventW` at `0x140049746`
- `KERNEL32!CreateEventW` at `0x140049793`
- `KERNEL32!GetLastError` at `0x140049755`
- `KERNEL32!GetLastError` at `0x1400497a2`
- `KERNEL32!GetLastError` at `0x140049814`
- `KERNEL32!GetLastError` at `0x140049755`
- `KERNEL32!GetLastError` at `0x1400497a2`
- `KERNEL32!GetLastError` at `0x140049814`

## pseudocode

```c
__int64 __fastcall CNTService::StartServiceW(CNTService *this)
{
  DWORD v2; // ebx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  HANDLE v5; // rax
  DWORD v6; // eax
  PVOID *v7; // r10
  DWORD v8; // eax
  SERVICE_TABLE_ENTRYW ServiceStartTable; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+30h] [rbp-38h]
  __int64 v12; // [rsp+38h] [rbp-30h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
  v2 = 0;
  ServiceStartTable.lpServiceName = (LPWSTR)*((_QWORD *)this + 5);
  v11 = 0;
  ServiceStartTable.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)CNTService::ServiceMain;
  v12 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 10) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, LastError);
    }
  }
  v5 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 11) = v5;
  if ( v5 )
    goto LABEL_14;
  v6 = GetLastError();
  v2 = v6;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v6);
LABEL_14:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v2 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 && *((_BYTE *)v7 + 25) >= 4u )
      WPP_SF_(v7[2], 74, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
    if ( StartServiceCtrlDispatcherW(&ServiceStartTable) )
      goto LABEL_25;
    v8 = GetLastError();
    v2 = v8;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v2;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v8);
LABEL_25:
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v7 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v7 + 28) & 1) != 0
    && *((unsigned __int8 *)v7 + 25) >= (unsigned int)(v2 != 0 ? 2 : 5) )
  {
    WPP_SF_d(v7[2], 76, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x1400496dc  push    rbx
0x1400496de  push    rbp
0x1400496df  push    rdi
0x1400496e0  push    r14
0x1400496e2  sub     rsp, 48h
0x1400496e6  mov     rdi, rcx
0x1400496e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400496f0  lea     rbp, WPP_GLOBAL_Control
0x1400496f7  lea     r14, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x1400496fe  cmp     rcx, rbp
0x140049701  jz      short loc_14004971A
0x140049703  test    byte ptr [rcx+1Ch], 1
0x140049707  jz      short loc_14004971A
0x140049709  mov     rcx, [rcx+10h]
0x14004970d  mov     edx, 47h ; 'G'
0x140049712  mov     r8, r14
0x140049715  call    WPP_SF_
0x14004971a  mov     rax, [rdi+28h]
0x14004971e  xor     ebx, ebx
0x140049720  mov     [rsp+68h+ServiceStartTable.lpServiceName], rax
0x140049725  xor     r9d, r9d; lpName
0x140049728  lea     rax, ?ServiceMain@CNTService@@SAXKPEAPEAG@Z; CNTService::ServiceMain(ulong,ushort * *)
0x14004972f  mov     [rsp+68h+var_38], rbx
0x140049734  xor     r8d, r8d; bInitialState
0x140049737  mov     [rsp+68h+ServiceStartTable.lpServiceProc], rax
0x14004973c  lea     edx, [rbx+1]; bManualReset
0x14004973f  mov     [rsp+68h+var_30], rbx
0x140049744  xor     ecx, ecx; lpEventAttributes
0x140049746  call    cs:__imp_CreateEventW
0x14004974c  mov     [rdi+50h], rax
0x140049750  test    rax, rax
0x140049753  jnz     short loc_140049789
0x140049755  call    cs:__imp_GetLastError
0x14004975b  mov     ebx, eax
0x14004975d  mov     rcx, cs:WPP_GLOBAL_Control
0x140049764  cmp     rcx, rbp
0x140049767  jz      short loc_140049789
0x140049769  test    byte ptr [rcx+1Ch], 2
0x14004976d  jz      short loc_140049789
0x14004976f  cmp     byte ptr [rcx+19h], 2
0x140049773  jb      short loc_140049789
0x140049775  mov     rcx, [rcx+10h]
0x140049779  mov     edx, 48h ; 'H'
0x14004977e  mov     r9d, eax
0x140049781  mov     r8, r14
0x140049784  call    WPP_SF_d
0x140049789  xor     r9d, r9d; lpName
0x14004978c  xor     r8d, r8d; bInitialState
0x14004978f  xor     edx, edx; bManualReset
0x140049791  xor     ecx, ecx; lpEventAttributes
0x140049793  call    cs:__imp_CreateEventW
0x140049799  mov     [rdi+58h], rax
0x14004979d  test    rax, rax
0x1400497a0  jnz     short loc_1400497D8
0x1400497a2  call    cs:__imp_GetLastError
0x1400497a8  mov     ebx, eax
0x1400497aa  mov     r10, cs:WPP_GLOBAL_Control
0x1400497b1  cmp     r10, rbp
0x1400497b4  jz      short loc_1400497DF
0x1400497b6  test    byte ptr [r10+1Ch], 2
0x1400497bb  jz      short loc_1400497DF
0x1400497bd  cmp     byte ptr [r10+19h], 2
0x1400497c2  jb      short loc_1400497DF
0x1400497c4  mov     rcx, [r10+10h]
0x1400497c8  mov     edx, 49h ; 'I'
0x1400497cd  mov     r9d, eax
0x1400497d0  mov     r8, r14
0x1400497d3  call    WPP_SF_d
0x1400497d8  mov     r10, cs:WPP_GLOBAL_Control
0x1400497df  test    ebx, ebx
0x1400497e1  jnz     short loc_140049851
0x1400497e3  cmp     r10, rbp
0x1400497e6  jz      short loc_140049805
0x1400497e8  test    byte ptr [r10+1Ch], 2
0x1400497ed  jz      short loc_140049805
0x1400497ef  cmp     byte ptr [r10+19h], 4
0x1400497f4  jb      short loc_140049805
0x1400497f6  mov     rcx, [r10+10h]
0x1400497fa  lea     edx, [rbx+4Ah]
0x1400497fd  mov     r8, r14
0x140049800  call    WPP_SF_
0x140049805  lea     rcx, [rsp+68h+ServiceStartTable]; lpServiceStartTable
0x14004980a  call    cs:__imp_StartServiceCtrlDispatcherW
0x140049810  test    eax, eax
0x140049812  jnz     short loc_14004984A
0x140049814  call    cs:__imp_GetLastError
0x14004981a  mov     ebx, eax
0x14004981c  mov     r10, cs:WPP_GLOBAL_Control
0x140049823  cmp     r10, rbp
0x140049826  jz      short loc_140049886
0x140049828  test    byte ptr [r10+1Ch], 2
0x14004982d  jz      short loc_140049851
0x14004982f  cmp     byte ptr [r10+19h], 2
0x140049834  jb      short loc_140049851
0x140049836  mov     rcx, [r10+10h]
0x14004983a  mov     edx, 4Bh ; 'K'
0x14004983f  mov     r9d, eax
0x140049842  mov     r8, r14
0x140049845  call    WPP_SF_d
0x14004984a  mov     r10, cs:WPP_GLOBAL_Control
0x140049851  cmp     r10, rbp
0x140049854  jz      short loc_140049886
0x140049856  test    byte ptr [r10+1Ch], 1
0x14004985b  jz      short loc_140049886
0x14004985d  movzx   edx, byte ptr [r10+19h]
0x140049862  mov     eax, ebx
0x140049864  neg     eax
0x140049866  sbb     ecx, ecx
0x140049868  and     ecx, 0FFFFFFFDh
0x14004986b  add     ecx, 5
0x14004986e  cmp     edx, ecx
0x140049870  jb      short loc_140049886
0x140049872  mov     rcx, [r10+10h]
0x140049876  mov     edx, 4Ch ; 'L'
0x14004987b  mov     r9d, ebx
0x14004987e  mov     r8, r14
0x140049881  call    WPP_SF_d
0x140049886  mov     eax, ebx
0x140049888  add     rsp, 48h
0x14004988c  pop     r14
0x14004988e  pop     rdi
0x14004988f  pop     rbp
0x140049890  pop     rbx
0x140049891  retn
```
