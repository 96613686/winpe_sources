# UlAtqInitialize(ushort const *,ushort const *,MULTISZ *,ulong,_ULATQ_CONFIG *,int,ulong)

- ea: `0x180015660`
- end: `0x180015805`
- name: `?UlAtqInitialize@@YAJPEBG0PEAVMULTISZ@@KPEAU_ULATQ_CONFIG@@HK@Z`
- size: `421`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct MULTISZ *, unsigned int, struct _ULATQ_CONFIG *, int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001060`
- `0x18001358c`
- `0x1800146a4`
- `0x180015434`
- `0x180015660`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800156a6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800156a6`
- `HTTPAPI!HttpTerminate` at `0x1800157f0`
- `HTTPAPI!HttpTerminate` at `0x1800157f0`
- `HTTPAPI!HttpInitialize` at `0x1800156fd`
- `HTTPAPI!HttpInitialize` at `0x1800156fd`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x1800156b8`
- `iisutil!PuLoadDebugFlagsFromRegStr` at `0x1800156b8`
- `iisutil!PuCreateDebugPrintsObject` at `0x18001568d`
- `iisutil!PuCreateDebugPrintsObject` at `0x18001568d`
- `iisutil!IISGetPlatformType` at `0x1800156c4`
- `iisutil!IISGetPlatformType` at `0x1800156c4`
- `iisutil!PuDbgPrint` at `0x180015750`
- `iisutil!PuDbgPrint` at `0x180015750`

## string_xrefs

- `0x18001569f`: `Unable to Create Debug Print Object \n`
- `0x180015749`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\main.cxx`
- `0x1800156b1`: `System\CurrentControlSet\Services\w3svc\Parameters\w3dt`

## pseudocode

```c
__int64 __fastcall UlAtqInitialize(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct MULTISZ *a3,
        unsigned int a4,
        struct _ULATQ_CONFIG *a5,
        int a6,
        unsigned int a7)
{
  signed int v11; // eax
  unsigned int v12; // edx
  unsigned int v13; // ebx
  int v14; // edi
  WP_CONTEXT *v15; // rax
  WP_CONTEXT *v16; // rcx
  int v17; // eax

  g_pDebug = PuCreateDebugPrintsObject("w3dt", 9);
  if ( !g_pDebug )
    OutputDebugStringA("Unable to Create Debug Print Object \n");
  g_dwDebugFlags = PuLoadDebugFlagsFromRegStr("System\\CurrentControlSet\\Services\\w3svc\\Parameters\\w3dt", 8);
  IISGetPlatformType();
  g_pfnNewRequest = (enum NREQ_STATUS (__high *)(void *))*((_QWORD *)a5 + 1);
  g_pfnIoCompletion = *(enum NREQ_STATUS (__high **)(unsigned int, void *, unsigned int, unsigned int, struct _OVERLAPPED *))a5;
  g_pfnDisconnect = (void (*)(void *))*((_QWORD *)a5 + 2);
  v11 = HttpInitialize((HTTPAPI_VERSION)2, 1u, 0);
  v13 = v11;
  if ( v11 )
  {
    v14 = 0;
    if ( v11 > 0 )
      v13 = (unsigned __int16)v11 | 0x80070000;
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\main.cxx",
        121,
        "UlAtqInitialize",
        "Error (rc=%08x) in UlInitialize. Exiting\n",
        v13);
    goto LABEL_15;
  }
  v14 = 1;
  v15 = (WP_CONTEXT *)operator new(0x4E8u);
  if ( !v15 )
  {
    g_pwpContext = 0;
    goto LABEL_14;
  }
  g_pwpContext = WP_CONTEXT::WP_CONTEXT(v15);
  if ( !g_pwpContext )
  {
LABEL_14:
    v13 = -2147024888;
    goto LABEL_15;
  }
  v17 = WP_CONTEXT::Initialize(v16, a1, a2, a3, a4, a6, a7);
  v13 = v17;
  if ( !v17 )
    return v13;
  if ( v17 > 0 )
    v13 = (unsigned __int16)v17 | 0x80070000;
LABEL_15:
  if ( g_pwpContext )
  {
    WP_CONTEXT::`scalar deleting destructor'(g_pwpContext, v12);
    g_pwpContext = 0;
  }
  if ( v14 )
    HttpTerminate(1u, 0);
  return v13;
}

```

## disassembly

```asm
0x180015660  push    rbx
0x180015662  push    rbp
0x180015663  push    rsi
0x180015664  push    rdi
0x180015665  push    r14
0x180015667  push    r15
0x180015669  sub     rsp, 58h
0x18001566d  mov     r14, rdx
0x180015670  mov     dword ptr [rsp+88h+Version.HttpApiMajorVersion], 2
0x180015678  mov     r15, rcx
0x18001567b  mov     edx, 9
0x180015680  lea     rcx, aW3dt; "w3dt"
0x180015687  mov     esi, r9d
0x18001568a  mov     rbp, r8
0x18001568d  call    cs:__imp_PuCreateDebugPrintsObject
0x180015693  mov     cs:g_pDebug, rax
0x18001569a  test    rax, rax
0x18001569d  jnz     short loc_1800156AC
0x18001569f  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x1800156a6  call    cs:__imp_OutputDebugStringA
0x1800156ac  mov     edx, 8
0x1800156b1  lea     rcx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\w3"...
0x1800156b8  call    cs:__imp_PuLoadDebugFlagsFromRegStr
0x1800156be  mov     cs:g_dwDebugFlags, eax
0x1800156c4  call    cs:__imp_IISGetPlatformType
0x1800156ca  mov     rcx, [rsp+88h+arg_20]
0x1800156d2  xor     r8d, r8d; pReserved
0x1800156d5  mov     rax, [rcx+8]
0x1800156d9  lea     edx, [r8+1]; Flags
0x1800156dd  mov     cs:?g_pfnNewRequest@@3P6A?AW4NREQ_STATUS@@PEAX@ZEA, rax; NREQ_STATUS (*g_pfnNewRequest)(void *)
0x1800156e4  mov     rax, [rcx]
0x1800156e7  mov     cs:?g_pfnIoCompletion@@3P6A?AW4NREQ_STATUS@@KPEAXKKPEAU_OVERLAPPED@@@ZEA, rax; NREQ_STATUS (*g_pfnIoCompletion)(ulong,void *,ulong,ulong,_OVERLAPPED *)
0x1800156ee  mov     rax, [rcx+10h]
0x1800156f2  mov     ecx, dword ptr [rsp+88h+Version.HttpApiMajorVersion]; Version
0x1800156f6  mov     cs:?g_pfnDisconnect@@3P6AXPEAX@ZEA, rax; void (*g_pfnDisconnect)(void *)
0x1800156fd  call    cs:__imp_HttpInitialize
0x180015703  mov     ebx, eax
0x180015705  test    eax, eax
0x180015707  jz      short loc_180015758
0x180015709  xor     edi, edi
0x18001570b  test    eax, eax
0x18001570d  jle     short loc_180015718
0x18001570f  movzx   ebx, ax
0x180015712  or      ebx, 80070000h
0x180015718  test    byte ptr cs:g_dwDebugFlags, 3
0x18001571f  jz      loc_1800157CB
0x180015725  mov     rcx, cs:g_pDebug
0x18001572c  lea     rax, aErrorRc08xInUl; "Error (rc=%08x) in UlInitialize. Exitin"...
0x180015733  mov     [rsp+88h+var_60], ebx
0x180015737  lea     r9, aUlatqinitializ_0; "UlAtqInitialize"
0x18001573e  mov     r8d, 79h ; 'y'
0x180015744  mov     qword ptr [rsp+88h+var_68], rax
0x180015749  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180015750  call    cs:__imp_PuDbgPrint
0x180015756  jmp     short loc_1800157CB
0x180015758  mov     ecx, 4E8h; Size
0x18001575d  mov     edi, 1
0x180015762  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015767  test    rax, rax
0x18001576a  jz      short loc_1800157BB
0x18001576c  mov     rcx, rax; this
0x18001576f  call    ??0WP_CONTEXT@@QEAA@XZ; WP_CONTEXT::WP_CONTEXT(void)
0x180015774  mov     cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA, rax; WP_CONTEXT * g_pwpContext
0x18001577b  test    rax, rax
0x18001577e  jz      short loc_1800157C6
0x180015780  mov     eax, [rsp+88h+arg_30]
0x180015787  mov     r9, rbp; struct MULTISZ *
0x18001578a  mov     [rsp+88h+var_58], eax; unsigned int
0x18001578e  mov     r8, r14; unsigned __int16 *
0x180015791  mov     eax, [rsp+88h+arg_28]
0x180015798  mov     rdx, r15; unsigned __int16 *
0x18001579b  mov     [rsp+88h+var_60], eax; int
0x18001579f  mov     [rsp+88h+var_68], esi; unsigned int
0x1800157a3  call    ?Initialize@WP_CONTEXT@@QEAAJPEBG0PEAVMULTISZ@@KHK@Z; WP_CONTEXT::Initialize(ushort const *,ushort const *,MULTISZ *,ulong,int,ulong)
0x1800157a8  mov     ebx, eax
0x1800157aa  test    eax, eax
0x1800157ac  jz      short loc_1800157F6
0x1800157ae  jle     short loc_1800157CB
0x1800157b0  movzx   ebx, ax
0x1800157b3  or      ebx, 80070000h
0x1800157b9  jmp     short loc_1800157CB
0x1800157bb  mov     cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA, 0; WP_CONTEXT * g_pwpContext
0x1800157c6  mov     ebx, 80070008h
0x1800157cb  mov     rcx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; this
0x1800157d2  test    rcx, rcx
0x1800157d5  jz      short loc_1800157E7
0x1800157d7  call    ??_GWP_CONTEXT@@QEAAPEAXI@Z; WP_CONTEXT::`scalar deleting destructor'(uint)
0x1800157dc  mov     cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA, 0; WP_CONTEXT * g_pwpContext
0x1800157e7  test    edi, edi
0x1800157e9  jz      short loc_1800157F6
0x1800157eb  xor     edx, edx; pReserved
0x1800157ed  lea     ecx, [rdx+1]; Flags
0x1800157f0  call    cs:__imp_HttpTerminate
0x1800157f6  mov     eax, ebx
0x1800157f8  add     rsp, 58h
0x1800157fc  pop     r15
0x1800157fe  pop     r14
0x180015800  pop     rdi
0x180015801  pop     rsi
0x180015802  pop     rbp
0x180015803  pop     rbx
0x180015804  retn
```
