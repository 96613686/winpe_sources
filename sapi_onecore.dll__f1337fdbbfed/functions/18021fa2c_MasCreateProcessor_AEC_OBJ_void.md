# MasCreateProcessor(AEC_OBJ *,void * *)

- ea: `0x18021fa2c`
- end: `0x18021fc9d`
- name: `?MasCreateProcessor@@YAHPEAUAEC_OBJ@@PEAPEAX@Z`
- size: `625`
- prototype: `__int64 __fastcall(struct AEC_OBJ *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18020952c`

## callees

- `0x180079e30`
- `0x18007aae4`
- `0x1801e6000`
- `0x18021f7fc`
- `0x18021fa2c`
- `0x18021fca4`
- `0x18021fcc0`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18021fb18`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18021fb4c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18021fb83`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18021fbba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18021fbf7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18021fb18`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18021fb4c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18021fb83`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18021fbba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18021fbf7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021fb0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021fb3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021fb75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021fbac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021fbe6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021fb0a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021fb3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021fb75`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021fbac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18021fbe6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18021fae0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18021fae0`

## string_xrefs

- `0x18021fac1`: `MasCreateProcessor`
- `0x18021fc5a`: `MasCreateProcessor`
- `0x18021fad9`: `coremas.dll`
- `0x18021fbdf`: `CreateUnimicProcessor`
- `0x18021fba5`: `DeleteUnimicProcessor`

## pseudocode

```c
__int64 __fastcall MasCreateProcessor(struct AEC_OBJ *a1, void **a2)
{
  __int64 v4; // r15
  unsigned __int64 MicChannelCount; // r13
  struct AEC_OBJ *v6; // rcx
  unsigned int v7; // ebx
  int v8; // r9d
  const char *v9; // r8
  HMODULE LibraryA; // rax
  HMODULE v11; // rdi
  FARPROC ProcAddress; // rax
  FARPROC v13; // rax
  FARPROC v14; // rax
  FARPROC v15; // rax
  FARPROC v16; // r14
  unsigned __int64 RefChannelCount; // [rsp+30h] [rbp-858h]
  _QWORD v19[3]; // [rsp+38h] [rbp-850h] BYREF
  _BYTE v20[2048]; // [rsp+50h] [rbp-838h] BYREF

  v4 = *((_DWORD *)a1 + 373) != 0 ? 0x200 : 0;
  MicChannelCount = MasGetMicChannelCount(a1);
  RefChannelCount = MasGetRefChannelCount(v6);
  v19[0] = MicChannelCount;
  v19[1] = RefChannelCount;
  memset_0(v20, 0, sizeof(v20));
  v7 = -2147467261;
  if ( a2 )
  {
    LibraryA = LoadLibraryA("coremas.dll");
    v11 = LibraryA;
    if ( LibraryA )
    {
      ProcAddress = GetProcAddress(LibraryA, "GetUnimicProcessorOutputChannelCount");
      if ( ProcAddress )
      {
        *((_QWORD *)a1 + 854) = ProcAddress;
        v13 = GetProcAddress(v11, "GetUnimicProcessorInputChannelCount");
        if ( v13 )
        {
          *((_QWORD *)a1 + 855) = v13;
          v14 = GetProcAddress(v11, "RunUnimicProcessor");
          if ( v14 )
          {
            *((_QWORD *)a1 + 856) = v14;
            v15 = GetProcAddress(v11, "DeleteUnimicProcessor");
            if ( v15 )
            {
              v7 = a1 == 0 ? 0x80004003 : 0;
              *((_QWORD *)a1 + 857) = v15;
              v16 = GetProcAddress(v11, "CreateUnimicProcessor");
              if ( v16 )
              {
                MasComputeProcessorSpec(a1, MicChannelCount, RefChannelCount, v20);
                *a2 = (void *)((__int64 (__fastcall *)(_BYTE *, __int64, _QWORD *, __int64))v16)(v20, 2, v19, v4 + 1280);
                return v7;
              }
              FreeLibrary(v11);
              v8 = -2147483381;
              v7 = -2147483381;
              v9 = "210";
            }
            else
            {
              FreeLibrary(v11);
              v8 = -2147483381;
              v7 = -2147483381;
              v9 = "203";
            }
          }
          else
          {
            FreeLibrary(v11);
            v8 = -2147483381;
            v7 = -2147483381;
            v9 = "196";
          }
        }
        else
        {
          FreeLibrary(v11);
          v8 = -2147483381;
          v7 = -2147483381;
          v9 = "189";
        }
      }
      else
      {
        FreeLibrary(v11);
        v8 = -2147483381;
        v7 = -2147483381;
        v9 = "182";
      }
    }
    else
    {
      v8 = -2147483381;
      v7 = -2147483381;
      v9 = "176";
    }
  }
  else
  {
    v8 = -2147467261;
    v9 = "172";
  }
  DumpTraceWin32("Function %s(%s) : *** TRACE *** code = 0x%x!\n", "MasCreateProcessor", v9, v8);
  return v7;
}

```

## disassembly

```asm
0x18021fa2c  mov     [rsp+arg_10], rbx
0x18021fa31  mov     [rsp+arg_18], rsi
0x18021fa36  push    rdi
0x18021fa37  push    r12
0x18021fa39  push    r13
0x18021fa3b  push    r14
0x18021fa3d  push    r15
0x18021fa3f  sub     rsp, 860h
0x18021fa46  mov     rax, cs:__security_cookie
0x18021fa4d  xor     rax, rsp
0x18021fa50  mov     [rsp+888h+var_38], rax
0x18021fa58  mov     r12, rdx
0x18021fa5b  mov     rsi, rcx
0x18021fa5e  mov     eax, [rcx+5D4h]
0x18021fa64  neg     eax
0x18021fa66  sbb     r15, r15
0x18021fa69  and     r15d, 200h
0x18021fa70  call    ?MasGetMicChannelCount@@YA_KPEAUAEC_OBJ@@@Z; MasGetMicChannelCount(AEC_OBJ *)
0x18021fa75  mov     r13, rax
0x18021fa78  call    ?MasGetRefChannelCount@@YA_KPEAUAEC_OBJ@@@Z; MasGetRefChannelCount(AEC_OBJ *)
0x18021fa7d  mov     [rsp+888h+var_858], rax
0x18021fa82  mov     [rsp+888h+var_850], r13
0x18021fa87  mov     [rsp+888h+var_848], rax
0x18021fa8c  xor     edx, edx; Val
0x18021fa8e  mov     r8d, 800h; Size
0x18021fa94  lea     rcx, [rsp+888h+var_838]; void *
0x18021fa99  call    memset_0
0x18021fa9e  mov     rcx, rsi
0x18021faa1  neg     rcx
0x18021faa4  sbb     r14d, r14d
0x18021faa7  not     r14d
0x18021faaa  mov     ebx, 80004003h
0x18021faaf  and     r14d, ebx
0x18021fab2  test    r12, r12
0x18021fab5  jnz     short loc_18021FAD9
0x18021fab7  mov     r9d, ebx; int
0x18021faba  lea     r8, a172; "172"
0x18021fac1  lea     rdx, aMascreateproce; "MasCreateProcessor"
0x18021fac8  lea     rcx, aFunctionSSTrac_0; "Function %s(%s) : *** TRACE *** code = "...
0x18021facf  call    ?DumpTraceWin32@@YAXPEBD00H@Z; DumpTraceWin32(char const *,char const *,char const *,int)
0x18021fad4  jmp     loc_18021FC6E
0x18021fad9  lea     rcx, aCoremasDll; "coremas.dll"
0x18021fae0  call    cs:__imp_LoadLibraryA
0x18021fae6  mov     rdi, rax
0x18021fae9  test    rax, rax
0x18021faec  jnz     short loc_18021FB00
0x18021faee  mov     r9d, 8000010Bh
0x18021faf4  mov     ebx, r9d
0x18021faf7  lea     r8, a176; "176"
0x18021fafe  jmp     short loc_18021FAC1
0x18021fb00  lea     rdx, aGetunimicproce; "GetUnimicProcessorOutputChannelCount"
0x18021fb07  mov     rcx, rdi; hModule
0x18021fb0a  call    cs:__imp_GetProcAddress
0x18021fb10  mov     rcx, rdi; hModule
0x18021fb13  test    rax, rax
0x18021fb16  jnz     short loc_18021FB30
0x18021fb18  call    cs:__imp_FreeLibrary
0x18021fb1e  mov     r9d, 8000010Bh
0x18021fb24  mov     ebx, r9d
0x18021fb27  lea     r8, a182; "182"
0x18021fb2e  jmp     short loc_18021FAC1
0x18021fb30  mov     [rsi+1AB0h], rax
0x18021fb37  lea     rdx, aGetunimicproce_0; "GetUnimicProcessorInputChannelCount"
0x18021fb3e  call    cs:__imp_GetProcAddress
0x18021fb44  mov     rcx, rdi; hModule
0x18021fb47  test    rax, rax
0x18021fb4a  jnz     short loc_18021FB67
0x18021fb4c  call    cs:__imp_FreeLibrary
0x18021fb52  mov     r9d, 8000010Bh
0x18021fb58  mov     ebx, r9d
0x18021fb5b  lea     r8, a189; "189"
0x18021fb62  jmp     loc_18021FAC1
0x18021fb67  mov     [rsi+1AB8h], rax
0x18021fb6e  lea     rdx, aRununimicproce; "RunUnimicProcessor"
0x18021fb75  call    cs:__imp_GetProcAddress
0x18021fb7b  mov     rcx, rdi; hModule
0x18021fb7e  test    rax, rax
0x18021fb81  jnz     short loc_18021FB9E
0x18021fb83  call    cs:__imp_FreeLibrary
0x18021fb89  mov     r9d, 8000010Bh
0x18021fb8f  mov     ebx, r9d
0x18021fb92  lea     r8, a196; "196"
0x18021fb99  jmp     loc_18021FAC1
0x18021fb9e  mov     [rsi+1AC0h], rax
0x18021fba5  lea     rdx, aDeleteunimicpr; "DeleteUnimicProcessor"
0x18021fbac  call    cs:__imp_GetProcAddress
0x18021fbb2  mov     rcx, rdi; hModule
0x18021fbb5  test    rax, rax
0x18021fbb8  jnz     short loc_18021FBD5
0x18021fbba  call    cs:__imp_FreeLibrary
0x18021fbc0  mov     r9d, 8000010Bh
0x18021fbc6  mov     ebx, r9d
0x18021fbc9  lea     r8, a203; "203"
0x18021fbd0  jmp     loc_18021FAC1
0x18021fbd5  mov     ebx, r14d
0x18021fbd8  mov     [rsi+1AC8h], rax
0x18021fbdf  lea     rdx, aCreateunimicpr; "CreateUnimicProcessor"
0x18021fbe6  call    cs:__imp_GetProcAddress
0x18021fbec  mov     r14, rax
0x18021fbef  test    rax, rax
0x18021fbf2  jnz     short loc_18021FC12
0x18021fbf4  mov     rcx, rdi; hLibModule
0x18021fbf7  call    cs:__imp_FreeLibrary
0x18021fbfd  mov     r9d, 8000010Bh
0x18021fc03  mov     ebx, r9d
0x18021fc06  lea     r8, a210; "210"
0x18021fc0d  jmp     loc_18021FAC1
0x18021fc12  lea     r9, [rsp+888h+var_838]
0x18021fc17  mov     r8, [rsp+888h+var_858]
0x18021fc1c  mov     rdx, r13
0x18021fc1f  mov     rcx, rsi
0x18021fc22  call    MasComputeProcessorSpec
0x18021fc27  lea     r9, [r15+500h]
0x18021fc2e  lea     r8, [rsp+888h+var_850]
0x18021fc33  mov     edx, 2
0x18021fc38  lea     rcx, [rsp+888h+var_838]
0x18021fc3d  mov     rax, r14
0x18021fc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021fc45  mov     [r12], rax
0x18021fc49  jmp     short loc_18021FC6E
0x18021fc4b  mov     ebx, 8000010Bh
0x18021fc50  mov     r9d, ebx; int
0x18021fc53  lea     r8, a220; "220"
0x18021fc5a  lea     rdx, aMascreateproce; "MasCreateProcessor"
0x18021fc61  lea     rcx, aFunctionSSTrac_0; "Function %s(%s) : *** TRACE *** code = "...
0x18021fc68  call    ?DumpTraceWin32@@YAXPEBD00H@Z; DumpTraceWin32(char const *,char const *,char const *,int)
0x18021fc6d  nop
0x18021fc6e  mov     eax, ebx
0x18021fc70  mov     rcx, [rsp+888h+var_38]
0x18021fc78  xor     rcx, rsp; StackCookie
0x18021fc7b  call    __security_check_cookie
0x18021fc80  lea     r11, [rsp+888h+var_28]
0x18021fc88  mov     rbx, [r11+40h]
0x18021fc8c  mov     rsi, [r11+48h]
0x18021fc90  mov     rsp, r11
0x18021fc93  pop     r15
0x18021fc95  pop     r14
0x18021fc97  pop     r13
0x18021fc99  pop     r12
0x18021fc9b  pop     rdi
0x18021fc9c  retn
```
