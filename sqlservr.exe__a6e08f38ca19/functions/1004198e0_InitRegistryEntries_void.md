# InitRegistryEntries(void)

- ea: `0x1004198e0`
- end: `0x100419a12`
- name: `?InitRegistryEntries@@YAXXZ`
- size: `306`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x100419a20`
- `0x100419c70`

## callees

- `0x1004198e0`
- `0x10044aad0`

## import_xrefs

- `instapi160!GetInstRegPathByID` at `0x100419908`
- `instapi160!GetInstRegPathByID` at `0x100419945`
- `instapi160!GetInstRegPathByID` at `0x100419982`
- `instapi160!GetInstRegPathByID` at `0x1004199bf`
- `instapi160!GetInstRegPathByID` at `0x100419908`
- `instapi160!GetInstRegPathByID` at `0x100419945`
- `instapi160!GetInstRegPathByID` at `0x100419982`
- `instapi160!GetInstRegPathByID` at `0x1004199bf`
- `instapi160!GetInstRootRegPathByID` at `0x1004199f7`
- `instapi160!GetInstRootRegPathByID` at `0x1004199f7`

## string_xrefs

- `0x100419912`: `Error getting service registry base key.`
- `0x10041998c`: `Error getting setup registry base key.`
- `0x10041994f`: `Error getting cluster registry base key.`
- `0x100419a01`: `Error getting registry base key.`
- `0x1004199c9`: `Error getting providers registry base key.`

## pseudocode

```c
void InitRegistryEntries(void)
{
  int v0; // [rsp+30h] [rbp+8h] BYREF

  v0 = 261;
  if ( !(unsigned int)GetInstRegPathByID(&GlobalInstanceId, 0, (char *)qword_10049F360 + 44300, &v0) )
    FailAndExit("Error getting service registry base key.");
  v0 = 261;
  if ( !(unsigned int)GetInstRegPathByID(&GlobalInstanceId, 4, (char *)qword_10049F360 + 46910, &v0) )
    FailAndExit("Error getting cluster registry base key.");
  v0 = 261;
  if ( !(unsigned int)GetInstRegPathByID(&GlobalInstanceId, 6, (char *)qword_10049F360 + 44822, &v0) )
    FailAndExit("Error getting setup registry base key.");
  v0 = 261;
  if ( !(unsigned int)GetInstRegPathByID(&GlobalInstanceId, 7, (char *)qword_10049F360 + 47432, &v0) )
    FailAndExit("Error getting providers registry base key.");
  v0 = 261;
  if ( !(unsigned int)GetInstRootRegPathByID(&GlobalInstanceId, (char *)qword_10049F360 + 47954, &v0) )
    FailAndExit("Error getting registry base key.");
}

```

## disassembly

```asm
0x1004198e0  sub     rsp, 28h
0x1004198e4  mov     r8, cs:qword_10049F360
0x1004198eb  lea     r9, [rsp+28h+arg_0]
0x1004198f0  add     r8, 0AD0Ch
0x1004198f7  mov     [rsp+28h+arg_0], 105h
0x1004198ff  xor     edx, edx
0x100419901  lea     rcx, ?GlobalInstanceId@@3U_INST_ID@@A; _INST_ID GlobalInstanceId
0x100419908  call    cs:__imp_GetInstRegPathByID
0x10041990e  test    eax, eax
0x100419910  jnz     short loc_10041991E
0x100419912  lea     rcx, aErrorGettingSe_0; "Error getting service registry base key"...
0x100419919  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10041991e  mov     r8, cs:qword_10049F360
0x100419925  lea     r9, [rsp+28h+arg_0]
0x10041992a  add     r8, 0B73Eh
0x100419931  mov     [rsp+28h+arg_0], 105h
0x100419939  mov     edx, 4
0x10041993e  lea     rcx, ?GlobalInstanceId@@3U_INST_ID@@A; _INST_ID GlobalInstanceId
0x100419945  call    cs:__imp_GetInstRegPathByID
0x10041994b  test    eax, eax
0x10041994d  jnz     short loc_10041995B
0x10041994f  lea     rcx, aErrorGettingCl; "Error getting cluster registry base key"...
0x100419956  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x10041995b  mov     r8, cs:qword_10049F360
0x100419962  lea     r9, [rsp+28h+arg_0]
0x100419967  add     r8, 0AF16h
0x10041996e  mov     [rsp+28h+arg_0], 105h
0x100419976  mov     edx, 6
0x10041997b  lea     rcx, ?GlobalInstanceId@@3U_INST_ID@@A; _INST_ID GlobalInstanceId
0x100419982  call    cs:__imp_GetInstRegPathByID
0x100419988  test    eax, eax
0x10041998a  jnz     short loc_100419998
0x10041998c  lea     rcx, aErrorGettingSe; "Error getting setup registry base key."
0x100419993  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419998  mov     r8, cs:qword_10049F360
0x10041999f  lea     r9, [rsp+28h+arg_0]
0x1004199a4  add     r8, 0B948h
0x1004199ab  mov     [rsp+28h+arg_0], 105h
0x1004199b3  mov     edx, 7
0x1004199b8  lea     rcx, ?GlobalInstanceId@@3U_INST_ID@@A; _INST_ID GlobalInstanceId
0x1004199bf  call    cs:__imp_GetInstRegPathByID
0x1004199c5  test    eax, eax
0x1004199c7  jnz     short loc_1004199D5
0x1004199c9  lea     rcx, aErrorGettingPr; "Error getting providers registry base k"...
0x1004199d0  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x1004199d5  mov     rdx, cs:qword_10049F360
0x1004199dc  lea     r8, [rsp+28h+arg_0]
0x1004199e1  add     rdx, 0BB52h
0x1004199e8  mov     [rsp+28h+arg_0], 105h
0x1004199f0  lea     rcx, ?GlobalInstanceId@@3U_INST_ID@@A; _INST_ID GlobalInstanceId
0x1004199f7  call    cs:__imp_GetInstRootRegPathByID
0x1004199fd  test    eax, eax
0x1004199ff  jnz     short loc_100419A0D
0x100419a01  lea     rcx, aErrorGettingRe; "Error getting registry base key."
0x100419a08  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419a0d  add     rsp, 28h
0x100419a11  retn
```
